# ArcForges implementation

## Execution state

There is no single Current task. Implementation is a set of delivery tasks with typed prerequisites, and any number of workers may execute different ready tasks at the same time. The authoritative rules are the Design [delivery model](https://github.com/ArcForges/ArcForges-Design-B/blob/main/docs/planning/delivery/README.md) (decision P2-018); this document is the operating procedure.

- **Now:** the adoption stage has not run, so the only ready task is `ADOPT.01` (freeze the adoption baseline). Each repository's adoption task (`ADOPT.02`–`ADOPT.10`, and `ADOPT.11` for Design and Plan) then opens that repository's tasks; repositories open independently.
- **Accepted baseline:** WP00, WP01, WP02 and WP03.00–03.02 (tasks `GOV.01`–`GOV.03`, `CON.90`–`CON.92`), recorded as inherited by adoption.
- **Reported, unverified:** the user reported WP03.03 complete on 2026-09-23. No source, pull request or receipt was present when this plan was written; `ADOPT.03` locates and reviews it before `CON.02`/`CON.03` are recorded as inherited.
- **Find work:** `python tools/delivery.py ready --claims` (optionally `--lane <lane>`). The [task list](list.md) indexes every task; each lane file under [`tasks/`](tasks/) holds one self-contained prompt per task.

## Project background

ArcForges is a family of commercially operable applications and shared services. ArcNotes provides knowledge management, ArcScope instrument acquisition and analysis, and ArcSlate media production. These are independent Avalonia/C# desktop applications. Each owns its application state, conversations, storage and server session, and embeds reusable assistant UI and mechanisms published by DesktopPlatform. ArcChat is the assistant/companion feature name, not a fourth desktop executable or a shared application hub.

Nine independent repositories integrate immutable published artifacts. DesktopPlatform provides shared managed mechanisms, Avalonia UI packages, native C ABI wrappers and RID runtimes; product domain behavior remains with its product owner. Contracts owns authored proto and generates C# NuGet, TypeScript npm and Kotlin Maven packages. Public business clients use binary gRPC-Web, with the explicit authentication, object-transfer and provider protocol exceptions defined by Design.

The C# Native AOT business host runs in Cloudflare Containers behind Workers. D1 owns authoritative business data, Durable Objects coordinate, and R2 stores objects. The sole AI Harness runs in Cloudflare Workflows with Workers AI. Mobile uses Kotlin/Jetpack Compose for Android; Web uses React/TypeScript for Site, Account, Chat and Operations. Applications have independent sessions without sibling Device SSO. Private parent-owned helpers/extensions alone use the specified gRPC over Named Pipes/UDS. Cross-product collaboration is future-only.

The goal is the complete accepted commercial product: usable client workflows, correct contracts and transactions, permissions, failure recovery, real integration, distribution, support and commercial operation. Existing Hello World scaffolds and published probes are migration inputs; they do not prove completed product behavior.

## Authoritative material and source locations

Formal Design: `C:\MyFile\Projects\ArcForges-Design-B`. Read its repository instructions and current decisions. The planning entry points are `docs/planning/delivery/README.md` (delivery model), the task records in `docs/planning/delivery/lanes/`, `docs/planning/README.md`, `docs/planning/implementation-sequence.md` (principles and mock policy) and `docs/planning/producer-artifacts-and-integration.md`. Work packages in `docs/planning/work-packages/` are the obligation catalogue: a task's obligations link to the substeps whose "what must be fully done", testing requirements and completion gates it must satisfy. Concrete behavior is defined across `docs/requirements`, `docs/architecture` (including `contracts` and `data-model`), `docs/experience` and `docs/assurance`. Current accepted amendments govern older text; filenames and historical inventories do not override them. Deprecated-input bodies are excluded from implementation reading.

Implementation repositories are under `C:\MyFile\Projects\ArcForges`: DesktopPlatform, Contracts, ArcNotes, ArcScope, ArcSlate, Cloud, AI, Web and Mobile. Each is a separate Git repository; a task names its one owning repository and any other repository it touches.

Read-only reference sources are `C:\MyFile\Projects\AionUi`, `AFFiNE`, `siyuan`, `Serial-Studio`, `ArcVideo` and `ArcVideoFoundation`. Start with their completed matrices under Design's `docs/assurance/reference-coverage` and inspect the relevant source or drift only. Respect per-file licences, provenance and excluded subtrees; a rewrite does not erase upstream obligations. `C:\MyFile\Projects\StartArcForges` is a packaged-artifact layout/notice reference only: do not execute, unpack or reverse engineer its binaries. Reference features do not create additional product requirements.

The remote/web execution-prompt variants in this repository (`arcforges-implementation-remote.md`, `list-remote.md`) are excluded from this execution model and are not maintained; do not use them as execution authority.

## Selecting a task

1. Pull the Plan and Design primaries (clean fast-forward only) so the graph, views and ledger are current.
2. Run `python tools/delivery.py ready --claims`. A task is listed when its owning repository's adoption is complete, every contract/artifact/design prerequisite is delivered or complete, every release prerequisite is complete, and no claim branch exists.
3. Prefer tasks on the [critical path](https://github.com/ArcForges/ArcForges-Design-B/blob/main/docs/planning/delivery/schedule-analysis.md) and tasks that unblock many others; otherwise any ready task is valid. Check its declared shared resources: if another in-flight task holds an `exclusive` mode on the same resource, pick different work or coordinate with that resource's owner.

## Claiming a task

A claim is an atomic branch creation in this repository (DLV-26). From Git Bash in `C:\MyFile\Projects\Plan-B`:

```bash
T=CON.02; L=$(echo "$T" | tr 'A-Z' 'a-z'); WORKER="<your worker name>"
git fetch origin
BLOB=$(printf '{"task":"%s","claimant":"%s","claimedAt":"%s","leaseUntil":"%s","state":"claimed"}\n' \
  "$T" "$WORKER" "$(date -u +%FT%TZ)" "$(date -u -d '+2 days' +%FT%TZ)" | git hash-object -w --stdin)
TREE=$(printf '100644 blob %s\tclaim.json\n' "$BLOB" | git mktree)
git push origin "$(git commit-tree "$TREE" -m "Claim $T")":"refs/heads/claims/$L"
```

The push fails if `claims/<task>` already exists, so two workers can never own one task. To renew the lease, build a new claim blob and push `git commit-tree "$TREE" -p "origin/claims/$L" -m "Renew $T"` to the same ref (a fast-forward). To release, push a commit whose claim state is `released`. Keep claim branches; they are the claim history.

## Executing a task

- Read the task record and its prompt, every obligation it links, the prerequisite tasks' published outputs and the applicable repository instructions. Verify relevant facts, finish research and decisions, then establish one complete ordered plan before editing. Repair conflicting authoritative documentation through a Design pull request before dependent implementation.
- Work in a retained Git worktree of the owning repository on branch `task/<task-id>` (lower case). Title pull requests `[<TASK-ID>] <summary>` and link the task record in the body. Append to the task's open pull request rather than creating a parallel one.
- Stay inside the task's write scope. Touch a declared shared resource only through its owner protocol (generated baselines are regenerated after rebase, migrations are numbered at merge, registries are appended). An undeclared conflict discovered at merge is resolved by the repository integration owner and recorded as a planning change if it will recur.
- Consume producers only through published candidates: update the exact pin you need through a reviewed dependency change. Use only the substitutes the task lists; never register a substitute in a release composition.
- Preserve product behavior, package IDs, signing continuity, immutable releases and unrelated work. A genuine architecture conflict stops the task and is raised (D-001); the claim records the blocked state.

## Completing a task

1. Merge the task's pull requests after review with all retained applicable checks green, and confirm any producer candidate's publication receipt.
2. If a completion prerequisite is still open, record the task as `delivered`; it becomes `complete` when the prerequisite completes.
3. Open a Plan pull request that adds `ledger/tasks/<TASK-ID>.md` in the [ledger format](ledger/README.md): source commits, candidate identities, validation actually performed, local runtime evidence, substitutes still in use and untested coverage. Review and merge it (this repository has no CI). Several ledger records may share one pull request.
4. Push a final claim commit with state `complete` (or `delivered`). Package and gate acceptance records go to Design `docs/assurance` when a package closure or gate task completes.

## Interruption, blocking and takeover

- The claimant resumes from the retained worktree, branch and pull request and renews the lease.
- After a lease expires, another worker may take over only by appending a takeover commit to the existing claim branch (fast-forward; if the push fails, someone else moved it first). The new worker continues the same branch and pull request.
- A blocked task records the concrete missing input in its claim. A missing prerequisite or design gap becomes a planning change: edit the Design graph, run `python tools/delivery.py generate` and `check`, and merge the Design and Plan pull requests.

## Coordination roles

- **Repository integration owner** (one per repository): merge order compatible with prerequisites, shared-resource protocols, generated baselines, main health and candidate publication. There is no family-wide merge order.
- **Architecture Owner:** contract and design changes (PA-02) and planning changes to the graph.
- **Release Engineering Owner:** release tasks, production signing, feeds and store pointers.
- **Workers:** own one claimed task at a time each; review may be done by any other worker or owner.

## Execution and validation policy

This policy governs every task and the adoption stage. It follows Design P2-017 and the CI/local validation policy, as amended in coordination wording by P2-018.

- No macOS CI job, runner or matrix, including self-hosted, scheduled and manual workflows. Local macOS source support may remain; never claim an unproduced macOS artifact or unobserved platform result.
- No hosted physical-device/emulator, desktop GUI, browser E2E, live service/RPC, real inference/Workflow, installed-package consumer or public-release install/upgrade tests. Remove hidden default check/build/publish invocations and obsolete artifact/status dependencies.
- Retain necessary Windows/Linux compilation, Native AOT compilation, packaging, static/format/type/lint checks, targeted offline unit tests and non-duplicated security. Do not multiply identical checks across platforms without a platform-specific requirement.
- Runtime/E2E checks are explicit local opt-in only for affected behavior supported by the existing environment. Run once; repeat only for a new change or concrete unresolved finding. Record untested coverage without inventing success or turning an optional missing environment into a new provisioning task.
- Do not install/reinstall vcpkg, SDKs, emulators or toolchains solely to expand validation. Git hooks must not silently restore/build/test on every commit/push.
- No routine public package/archive/image/site downloads, repeated member/hash comparison or consumer execution. Retain lockfile integrity, required signing/licence/provenance checks and one necessary identity/integrity check at an actual publication handoff. Additional downloads require a concrete integrity/publication defect or explicit user request.
- Promote the original candidate. Use provider upload/deployment receipts and status/coordinate metadata; no public-byte polling. Maven main uses SNAPSHOT, and formal Central publication requires a deliberate tag.
- Do not create tags, republish, re-sign or allocate replacement versions solely for verification. Diagnose failures before rerunning; no blind retries.
- Documentation-only edits require consistency/link review without an additional local product-build or runtime-test cycle. Code repositories still run their existing applicable CI for documentation-only PRs. Keep AGENTS, active docs, workflow dependencies and actual release inventories synchronized. Preserve historical evidence as history, not as a rerun mandate.

## Network and resources

Use the normal network path. Do not configure proxy 7890 or another proxy. On a failed network operation, stop and report the exact operation rather than changing networking or repeatedly retrying. Do not invoke wsl.exe or WSL wrappers; use a directly available WSL terminal only if necessary. Run at most one CPU-heavy local build or test per workstation at a time and reuse existing caches; coding and review continue in parallel.

## Review and merge

Review each complete PR and fix findings. Documentation repositories that have no CI merge directly after review. In code repositories, every PR, including documentation-only changes, must run the existing applicable CI and may merge only after all retained latest-head checks succeed. Do not skip configured checks or weaken branch protection to merge documentation changes. Remove obsolete runtime/macOS job references rather than adding fake passing gates. Do not bypass retained build/security/signing failures.

Post-merge verification is limited to the expected merge commit, required build/publication/deployment job result and clean fast-forward primary update. Do not start another public-download/hash/install/device/browser/runtime cycle. Keep branches and worktrees, protect credentials and report actual results and material untested coverage. Deployment success is not a live test, and compilation is not physical-device or full commercial acceptance.
