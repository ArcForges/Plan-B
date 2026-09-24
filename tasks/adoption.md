# ArcForges delivery task prompts — Adoption stage

Generated from Design `docs/planning/delivery/delivery-graph.json` by `tools/delivery.py`; do not edit by hand.
Each block is self-contained. Claim a task only when `python tools/delivery.py ready` lists it and no claim branch exists,
then follow `arcforges-implementation.md`. Tasks are ordered by lane for reading; the order is not a schedule.

## Adoption stage

```text
Execute ArcForges delivery task ADOPT.01 — Freeze the adoption baseline.

Task record: C:\MyFile\Projects\ArcForges-Design-B\docs\planning\delivery\lanes\adoption.md (anchor task-adopt-01).
Delivery rules: C:\MyFile\Projects\ArcForges-Design-B\docs\planning\delivery\README.md; execution: C:\MyFile\Projects\Plan-B\arcforges-implementation.md.
Owning repository: C:\MyFile\Projects\Plan-B (integration owner: Plan integration owner).
Kind/size: adoption/S. Baseline: not-started.
Outcome: The Plan ledger records, for every repository, the main head, open pull requests and branches, the latest published candidate per registry, and the location of any reported but unmerged work (including the reported WP-03.03 completion), so every repository review starts from the same frozen inputs.

Obligations (authoritative definitions; satisfy exactly these parts and their tests/gates):
- P2-018 (adoption stage: baseline inputs): C:\MyFile\Projects\ArcForges-Design-B\docs\decisions\phase-2-specification-decisions.md, anchor rule-p2-018

Start prerequisites (each must be complete in the Plan ledger before claiming):
- none
Completion prerequisites (may start earlier; cannot complete before these are complete):
- none

Permitted write scope: Plan:ledger/adoption/baseline.md; Plan:ledger/README.md
Unblocks: ADOPT.02, ADOPT.03, ADOPT.04, ADOPT.05, ADOPT.06, ADOPT.07, ADOPT.08, ADOPT.09, ADOPT.10, ADOPT.11

Validation (P2-017; no macOS/hosted runtime, device, GUI, browser E2E, live-service, inference or installed-consumer CI): Read-only inspection of repositories, pull requests and registry receipts already recorded; no builds, downloads or runtime checks (P2-017).
Completion evidence for the ledger: Baseline record with exact commit identities per repository, open pull request list, latest candidate identities and the reported-work locations; reviewed and merged in the Plan repository.
```

```text
Execute ArcForges delivery task ADOPT.02 — Adopt DesktopPlatform.

Task record: C:\MyFile\Projects\ArcForges-Design-B\docs\planning\delivery\lanes\adoption.md (anchor task-adopt-02).
Delivery rules: C:\MyFile\Projects\ArcForges-Design-B\docs\planning\delivery\README.md; execution: C:\MyFile\Projects\Plan-B\arcforges-implementation.md.
Owning repository: C:\MyFile\Projects\ArcForges\DesktopPlatform (integration owner: DesktopPlatform integration owner).
Kind/size: adoption/M. Baseline: not-started.
Outcome: Every delivery task owned by DesktopPlatform is classified inherited, inherited with adjustment, gap or conflicting against the recorded baseline, with ledger records for inherited tasks and a recorded adjustment list, including the replacement of the design-policy graph check that still validates the retired work-package graph.

Obligations (authoritative definitions; satisfy exactly these parts and their tests/gates):
- P2-018 (adoption stage: DesktopPlatform review): C:\MyFile\Projects\ArcForges-Design-B\docs\decisions\phase-2-specification-decisions.md, anchor rule-p2-018

Start prerequisites (each must be complete in the Plan ledger before claiming):
- [artifact] ADOPT.01: frozen baseline record
Completion prerequisites (may start earlier; cannot complete before these are complete):
- none

Permitted write scope: Plan:ledger/adoption/DesktopPlatform.md; Plan:ledger/tasks/*.md

Validation (P2-017; no macOS/hosted runtime, device, GUI, browser E2E, live-service, inference or installed-consumer CI): Review of merged source, retained CI results and receipts only; no new builds, downloads or runtime checks unless a task's evidence field requires a never-run local check (P2-017).
Completion evidence for the ledger: Adoption report with one classification row per owned task, evidence references for inherited tasks, adjustment list and any conflicts raised under D-001.
```

```text
Execute ArcForges delivery task ADOPT.03 — Adopt Contracts and locate the reported capability and resource closure.

Task record: C:\MyFile\Projects\ArcForges-Design-B\docs\planning\delivery\lanes\adoption.md (anchor task-adopt-03).
Delivery rules: C:\MyFile\Projects\ArcForges-Design-B\docs\planning\delivery\README.md; execution: C:\MyFile\Projects\Plan-B\arcforges-implementation.md.
Owning repository: C:\MyFile\Projects\ArcForges\Contracts (integration owner: Contracts integration owner).
Kind/size: adoption/M. Baseline: not-started.
Outcome: Every delivery task owned by Contracts is classified against the recorded baseline; the work the user reported as completing WP-03.03 is located and reviewed like any task completion, and is recorded as inherited only if its source, retained checks, publication receipt and vectors satisfy the task's evidence field.

Obligations (authoritative definitions; satisfy exactly these parts and their tests/gates):
- P2-018 (adoption stage: Contracts review, including the reported WP-03.03 completion): C:\MyFile\Projects\ArcForges-Design-B\docs\decisions\phase-2-specification-decisions.md, anchor rule-p2-018

Start prerequisites (each must be complete in the Plan ledger before claiming):
- [artifact] ADOPT.01: frozen baseline record including the reported-work location
Completion prerequisites (may start earlier; cannot complete before these are complete):
- none

Permitted write scope: Plan:ledger/adoption/Contracts.md; Plan:ledger/tasks/*.md

Validation (P2-017; no macOS/hosted runtime, device, GUI, browser E2E, live-service, inference or installed-consumer CI): Review of merged source, retained CI results and publication receipts only (P2-017).
Completion evidence for the ledger: Adoption report with classification rows, the reviewed evidence for any inherited closure, and adjustments.
```

```text
Execute ArcForges delivery task ADOPT.04 — Adopt ArcNotes.

Task record: C:\MyFile\Projects\ArcForges-Design-B\docs\planning\delivery\lanes\adoption.md (anchor task-adopt-04).
Delivery rules: C:\MyFile\Projects\ArcForges-Design-B\docs\planning\delivery\README.md; execution: C:\MyFile\Projects\Plan-B\arcforges-implementation.md.
Owning repository: C:\MyFile\Projects\ArcForges\ArcNotes (integration owner: ArcNotes integration owner).
Kind/size: adoption/S. Baseline: not-started.
Outcome: Every ArcNotes delivery task is classified; bootstrap scaffolding is recorded as scaffolding, never as product completion.

Obligations (authoritative definitions; satisfy exactly these parts and their tests/gates):
- P2-018 (adoption stage: ArcNotes review): C:\MyFile\Projects\ArcForges-Design-B\docs\decisions\phase-2-specification-decisions.md, anchor rule-p2-018

Start prerequisites (each must be complete in the Plan ledger before claiming):
- [artifact] ADOPT.01: frozen baseline record
Completion prerequisites (may start earlier; cannot complete before these are complete):
- none

Permitted write scope: Plan:ledger/adoption/ArcNotes.md; Plan:ledger/tasks/*.md

Validation (P2-017; no macOS/hosted runtime, device, GUI, browser E2E, live-service, inference or installed-consumer CI): Review only (P2-017).
Completion evidence for the ledger: Adoption report with classification rows and adjustments.
```

```text
Execute ArcForges delivery task ADOPT.05 — Adopt ArcScope.

Task record: C:\MyFile\Projects\ArcForges-Design-B\docs\planning\delivery\lanes\adoption.md (anchor task-adopt-05).
Delivery rules: C:\MyFile\Projects\ArcForges-Design-B\docs\planning\delivery\README.md; execution: C:\MyFile\Projects\Plan-B\arcforges-implementation.md.
Owning repository: C:\MyFile\Projects\ArcForges\ArcScope (integration owner: ArcScope integration owner).
Kind/size: adoption/S. Baseline: not-started.
Outcome: Every ArcScope delivery task is classified; bootstrap scaffolding is recorded as scaffolding, never as product completion.

Obligations (authoritative definitions; satisfy exactly these parts and their tests/gates):
- P2-018 (adoption stage: ArcScope review): C:\MyFile\Projects\ArcForges-Design-B\docs\decisions\phase-2-specification-decisions.md, anchor rule-p2-018

Start prerequisites (each must be complete in the Plan ledger before claiming):
- [artifact] ADOPT.01: frozen baseline record
Completion prerequisites (may start earlier; cannot complete before these are complete):
- none

Permitted write scope: Plan:ledger/adoption/ArcScope.md; Plan:ledger/tasks/*.md

Validation (P2-017; no macOS/hosted runtime, device, GUI, browser E2E, live-service, inference or installed-consumer CI): Review only (P2-017).
Completion evidence for the ledger: Adoption report with classification rows and adjustments.
```

```text
Execute ArcForges delivery task ADOPT.06 — Adopt ArcSlate.

Task record: C:\MyFile\Projects\ArcForges-Design-B\docs\planning\delivery\lanes\adoption.md (anchor task-adopt-06).
Delivery rules: C:\MyFile\Projects\ArcForges-Design-B\docs\planning\delivery\README.md; execution: C:\MyFile\Projects\Plan-B\arcforges-implementation.md.
Owning repository: C:\MyFile\Projects\ArcForges\ArcSlate (integration owner: ArcSlate integration owner).
Kind/size: adoption/S. Baseline: not-started.
Outcome: Every ArcSlate delivery task is classified; bootstrap scaffolding is recorded as scaffolding, never as product completion.

Obligations (authoritative definitions; satisfy exactly these parts and their tests/gates):
- P2-018 (adoption stage: ArcSlate review): C:\MyFile\Projects\ArcForges-Design-B\docs\decisions\phase-2-specification-decisions.md, anchor rule-p2-018

Start prerequisites (each must be complete in the Plan ledger before claiming):
- [artifact] ADOPT.01: frozen baseline record
Completion prerequisites (may start earlier; cannot complete before these are complete):
- none

Permitted write scope: Plan:ledger/adoption/ArcSlate.md; Plan:ledger/tasks/*.md

Validation (P2-017; no macOS/hosted runtime, device, GUI, browser E2E, live-service, inference or installed-consumer CI): Review only (P2-017).
Completion evidence for the ledger: Adoption report with classification rows and adjustments.
```

```text
Execute ArcForges delivery task ADOPT.07 — Adopt Cloud.

Task record: C:\MyFile\Projects\ArcForges-Design-B\docs\planning\delivery\lanes\adoption.md (anchor task-adopt-07).
Delivery rules: C:\MyFile\Projects\ArcForges-Design-B\docs\planning\delivery\README.md; execution: C:\MyFile\Projects\Plan-B\arcforges-implementation.md.
Owning repository: C:\MyFile\Projects\ArcForges\Cloud (integration owner: Cloud integration owner).
Kind/size: adoption/M. Baseline: not-started.
Outcome: Every delivery task owned by Cloud (core, commerce, policy, operations, simulator, search and catalog modules) is classified against the recorded baseline, distinguishing the bootstrap host and deployed probe from product modules.

Obligations (authoritative definitions; satisfy exactly these parts and their tests/gates):
- P2-018 (adoption stage: Cloud review): C:\MyFile\Projects\ArcForges-Design-B\docs\decisions\phase-2-specification-decisions.md, anchor rule-p2-018

Start prerequisites (each must be complete in the Plan ledger before claiming):
- [artifact] ADOPT.01: frozen baseline record
Completion prerequisites (may start earlier; cannot complete before these are complete):
- none

Permitted write scope: Plan:ledger/adoption/Cloud.md; Plan:ledger/tasks/*.md

Validation (P2-017; no macOS/hosted runtime, device, GUI, browser E2E, live-service, inference or installed-consumer CI): Review of merged source, retained CI and deployment receipts only (P2-017); a deployment receipt is not a live test.
Completion evidence for the ledger: Adoption report with classification rows and adjustments.
```

```text
Execute ArcForges delivery task ADOPT.08 — Adopt AI.

Task record: C:\MyFile\Projects\ArcForges-Design-B\docs\planning\delivery\lanes\adoption.md (anchor task-adopt-08).
Delivery rules: C:\MyFile\Projects\ArcForges-Design-B\docs\planning\delivery\README.md; execution: C:\MyFile\Projects\Plan-B\arcforges-implementation.md.
Owning repository: C:\MyFile\Projects\ArcForges\AI (integration owner: AI integration owner).
Kind/size: adoption/S. Baseline: not-started.
Outcome: Every delivery task owned by AI is classified; the bootstrap Worker and Workflow scaffolding is recorded as scaffolding, never as Harness completion.

Obligations (authoritative definitions; satisfy exactly these parts and their tests/gates):
- P2-018 (adoption stage: AI review): C:\MyFile\Projects\ArcForges-Design-B\docs\decisions\phase-2-specification-decisions.md, anchor rule-p2-018

Start prerequisites (each must be complete in the Plan ledger before claiming):
- [artifact] ADOPT.01: frozen baseline record
Completion prerequisites (may start earlier; cannot complete before these are complete):
- none

Permitted write scope: Plan:ledger/adoption/AI.md; Plan:ledger/tasks/*.md

Validation (P2-017; no macOS/hosted runtime, device, GUI, browser E2E, live-service, inference or installed-consumer CI): Review only (P2-017).
Completion evidence for the ledger: Adoption report with classification rows and adjustments.
```

```text
Execute ArcForges delivery task ADOPT.09 — Adopt Web.

Task record: C:\MyFile\Projects\ArcForges-Design-B\docs\planning\delivery\lanes\adoption.md (anchor task-adopt-09).
Delivery rules: C:\MyFile\Projects\ArcForges-Design-B\docs\planning\delivery\README.md; execution: C:\MyFile\Projects\Plan-B\arcforges-implementation.md.
Owning repository: C:\MyFile\Projects\ArcForges\Web (integration owner: Web integration owner).
Kind/size: adoption/S. Baseline: not-started.
Outcome: Every delivery task owned by Web is classified, including the existing static-site generator and canonical-host Worker.

Obligations (authoritative definitions; satisfy exactly these parts and their tests/gates):
- P2-018 (adoption stage: Web review): C:\MyFile\Projects\ArcForges-Design-B\docs\decisions\phase-2-specification-decisions.md, anchor rule-p2-018

Start prerequisites (each must be complete in the Plan ledger before claiming):
- [artifact] ADOPT.01: frozen baseline record
Completion prerequisites (may start earlier; cannot complete before these are complete):
- none

Permitted write scope: Plan:ledger/adoption/Web.md; Plan:ledger/tasks/*.md

Validation (P2-017; no macOS/hosted runtime, device, GUI, browser E2E, live-service, inference or installed-consumer CI): Review only (P2-017).
Completion evidence for the ledger: Adoption report with classification rows and adjustments.
```

```text
Execute ArcForges delivery task ADOPT.10 — Adopt Mobile.

Task record: C:\MyFile\Projects\ArcForges-Design-B\docs\planning\delivery\lanes\adoption.md (anchor task-adopt-10).
Delivery rules: C:\MyFile\Projects\ArcForges-Design-B\docs\planning\delivery\README.md; execution: C:\MyFile\Projects\Plan-B\arcforges-implementation.md.
Owning repository: C:\MyFile\Projects\ArcForges\Mobile (integration owner: Mobile integration owner).
Kind/size: adoption/S. Baseline: not-started.
Outcome: Every delivery task owned by Mobile is classified, including the development package identity and the preview-only shared module.

Obligations (authoritative definitions; satisfy exactly these parts and their tests/gates):
- P2-018 (adoption stage: Mobile review): C:\MyFile\Projects\ArcForges-Design-B\docs\decisions\phase-2-specification-decisions.md, anchor rule-p2-018

Start prerequisites (each must be complete in the Plan ledger before claiming):
- [artifact] ADOPT.01: frozen baseline record
Completion prerequisites (may start earlier; cannot complete before these are complete):
- none

Permitted write scope: Plan:ledger/adoption/Mobile.md; Plan:ledger/tasks/*.md

Validation (P2-017; no macOS/hosted runtime, device, GUI, browser E2E, live-service, inference or installed-consumer CI): Review only (P2-017).
Completion evidence for the ledger: Adoption report with classification rows and adjustments.
```

```text
Execute ArcForges delivery task ADOPT.11 — Reconcile Design and Plan documentation for adoption.

Task record: C:\MyFile\Projects\ArcForges-Design-B\docs\planning\delivery\lanes\adoption.md (anchor task-adopt-11).
Delivery rules: C:\MyFile\Projects\ArcForges-Design-B\docs\planning\delivery\README.md; execution: C:\MyFile\Projects\Plan-B\arcforges-implementation.md.
Owning repository: C:\MyFile\Projects\ArcForges-Design-B (integration owner: Design integration owner). Also touches: Plan.
Kind/size: adoption/S. Baseline: not-started.
Outcome: Documentation findings that affect adoption decisions are resolved or scheduled (including the pre-existing corpus citation drift recorded in the adoption stage document), the generated views are confirmed current, and the ledger identifies the repositories whose adoption is complete.

Obligations (authoritative definitions; satisfy exactly these parts and their tests/gates):
- P2-018 (adoption stage: documentation reconciliation): C:\MyFile\Projects\ArcForges-Design-B\docs\decisions\phase-2-specification-decisions.md, anchor rule-p2-018

Start prerequisites (each must be complete in the Plan ledger before claiming):
- [artifact] ADOPT.01: frozen baseline record
Completion prerequisites (may start earlier; cannot complete before these are complete):
- none

Permitted write scope: Design:docs/**; Plan:ledger/adoption/documentation.md

Validation (P2-017; no macOS/hosted runtime, device, GUI, browser E2E, live-service, inference or installed-consumer CI): Documentation consistency and link review, delivery graph check and the existing corpus integrity check; no product builds (P2-017).
Completion evidence for the ledger: Reconciliation record with checker results and any planning-change pull requests.
```
