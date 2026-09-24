# ArcForges delivery task prompts — Adoption stage

Generated from Design `docs/planning/delivery/delivery-graph.json` by `tools/delivery.py`; do not edit by hand.
Each block is self-contained. Claim a task only when `python tools/delivery.py ready --claims` lists it,
then follow `arcforges-implementation.md`. Tasks are ordered by lane for reading; the order is not a schedule.

## Adoption stage

```text
Execute ArcForges delivery task ADOPT.01 — Freeze the adoption baseline.

Task record: C:\MyFile\Projects\ArcForges-Design-B\docs\planning\delivery\lanes\adoption.md (anchor task-adopt-01).
Delivery rules: C:\MyFile\Projects\ArcForges-Design-B\docs\planning\delivery\README.md; execution: C:\MyFile\Projects\Plan-B\arcforges-implementation.md.
Owning repository: C:\MyFile\Projects\Plan-B (integration owner: Plan integration owner).
Kind/size: adoption/S. Baseline: not-started.
Outcome: The Plan ledger records, for every repository, the main head, open pull requests and branches and the latest published candidate per registry, so every adoption slice starts from the same frozen inputs. The baseline is complete through WP-03.02; WP-03.03 has not started.

Obligations (authoritative definitions; satisfy exactly these parts and their tests/gates):
- P2-018 (adoption stage: baseline inputs): C:\MyFile\Projects\ArcForges-Design-B\docs\decisions\phase-2-specification-decisions.md, anchor rule-p2-018

Start prerequisites (before claiming, each contract/artifact/design prerequisite must be delivered or complete and each release prerequisite complete in the Plan ledger; DLV-24):
- none
Completion prerequisites (may start earlier; cannot complete before these are complete):
- none

Permitted write scope: Plan:ledger/adoption/baseline.md; Plan:ledger/README.md
Unblocks: ADOPT.02, ADOPT.02.app-composition, ADOPT.02.assistant, ADOPT.02.cloud, ADOPT.02.device-bridge, ADOPT.02.execution, ADOPT.02.extensions, ADOPT.02.foundation, ADOPT.02.governance, ADOPT.02.native, ADOPT.02.platform, ADOPT.02.policy, ADOPT.02.release, ADOPT.02.runtime-proofs, ADOPT.02.updater, ADOPT.03, ADOPT.03.contracts, ADOPT.03.extensions, ADOPT.03.governance, ADOPT.03.release, ADOPT.04, ADOPT.04.app-composition, ADOPT.04.arcnotes, ADOPT.04.governance, ADOPT.04.release, ADOPT.04.runtime-proofs, ADOPT.05, ADOPT.05.arcscope, ADOPT.05.governance, ADOPT.05.release, ADOPT.05.runtime-proofs, ADOPT.05.simulator, ADOPT.06, ADOPT.06.arcslate, ADOPT.06.governance, ADOPT.06.release, ADOPT.06.runtime-proofs, ADOPT.07, ADOPT.07.ai-routing, ADOPT.07.cloud, ADOPT.07.commerce, ADOPT.07.device-bridge, ADOPT.07.extensions, ADOPT.07.governance, ADOPT.07.harness, ADOPT.07.operations, ADOPT.07.policy, ADOPT.07.release, ADOPT.07.runtime-proofs, ADOPT.07.search, ADOPT.07.simulator, ADOPT.08, ADOPT.08.ai-routing, ADOPT.08.extensions, ADOPT.08.governance, ADOPT.08.harness, ADOPT.09, ADOPT.09.governance, ADOPT.09.operations, ADOPT.09.release, ADOPT.09.runtime-proofs, ADOPT.09.web, ADOPT.10, ADOPT.10.android, ADOPT.10.governance, ADOPT.10.release, ADOPT.10.runtime-proofs, ADOPT.11

Validation (P2-017; no macOS/hosted runtime, device, GUI, browser E2E, live-service, inference or installed-consumer CI): Read-only inspection of repositories, pull requests and registry receipts already recorded; no builds, downloads or runtime checks (P2-017).
Completion evidence for the ledger: Baseline record with exact commit identities per repository, open pull request list and latest candidate identities; reviewed and merged in the Plan repository.
```

```text
Execute ArcForges delivery task ADOPT.02 — Adopt DesktopPlatform.

Task record: C:\MyFile\Projects\ArcForges-Design-B\docs\planning\delivery\lanes\adoption.md (anchor task-adopt-02).
Delivery rules: C:\MyFile\Projects\ArcForges-Design-B\docs\planning\delivery\README.md; execution: C:\MyFile\Projects\Plan-B\arcforges-implementation.md.
Owning repository: C:\MyFile\Projects\ArcForges\DesktopPlatform (integration owner: DesktopPlatform integration owner).
Kind/size: adoption/S. Baseline: not-started.
Outcome: The repository-wide adoption facts for DesktopPlatform (main head, retained CI workflow inventory under P2-017, package identities and pins, shared roots and source inventory) are recorded once for its slices to cite, and the DesktopPlatform classification table is complete when every adoption slice of the repository is complete. The governance slice schedules the replacement of the design-policy graph check that still validates the retired work-package graph.

Obligations (authoritative definitions; satisfy exactly these parts and their tests/gates):
- P2-018 (adoption stage: DesktopPlatform repository record): C:\MyFile\Projects\ArcForges-Design-B\docs\decisions\phase-2-specification-decisions.md, anchor rule-p2-018

Adoption slices (claim, review and record each separately as ledger/tasks/<slice>.md; one pull request may carry several; each slice opens only its own repository lane; see the Design adoption stage):
- ADOPT.02.app-composition: Adopt DesktopPlatform: Application composition (opens 6 tasks)
- ADOPT.02.assistant: Adopt DesktopPlatform: Embedded assistant (opens 22 tasks)
- ADOPT.02.cloud: Adopt DesktopPlatform: Cloud core (opens 2 tasks)
- ADOPT.02.device-bridge: Adopt DesktopPlatform: Application presence and tool bridge (opens 3 tasks)
- ADOPT.02.execution: Adopt DesktopPlatform: Execution engine (opens 9 tasks)
- ADOPT.02.extensions: Adopt DesktopPlatform: Extension platform and integrations (opens 7 tasks)
- ADOPT.02.foundation: Adopt DesktopPlatform: Foundation values (opens 7 tasks)
- ADOPT.02.governance: Adopt DesktopPlatform: Family governance and policy tests (opens 4 tasks; records 3 accepted tasks as inherited)
- ADOPT.02.native: Adopt DesktopPlatform: Native producers and probes (opens 25 tasks)
- ADOPT.02.platform: Adopt DesktopPlatform: Desktop platform mechanisms (opens 56 tasks)
- ADOPT.02.policy: Adopt DesktopPlatform: Dynamic policy and configuration (opens 1 task)
- ADOPT.02.release: Adopt DesktopPlatform: Release readiness and family release (opens 2 tasks)
- ADOPT.02.runtime-proofs: Adopt DesktopPlatform: Runtime proofs (opens 4 tasks)
- ADOPT.02.updater: Adopt DesktopPlatform: Desktop distribution and update (opens 8 tasks)

Start prerequisites (before claiming, each contract/artifact/design prerequisite must be delivered or complete and each release prerequisite complete in the Plan ledger; DLV-24):
- [artifact] ADOPT.01: frozen baseline record
Completion prerequisites (may start earlier; cannot complete before these are complete):
- [integration] ADOPT.02.app-composition: slice recorded
- [integration] ADOPT.02.assistant: slice recorded
- [integration] ADOPT.02.cloud: slice recorded
- [integration] ADOPT.02.device-bridge: slice recorded
- [integration] ADOPT.02.execution: slice recorded
- [integration] ADOPT.02.extensions: slice recorded
- [integration] ADOPT.02.foundation: slice recorded
- [integration] ADOPT.02.governance: slice recorded
- [integration] ADOPT.02.native: slice recorded
- [integration] ADOPT.02.platform: slice recorded
- [integration] ADOPT.02.policy: slice recorded
- [integration] ADOPT.02.release: slice recorded
- [integration] ADOPT.02.runtime-proofs: slice recorded
- [integration] ADOPT.02.updater: slice recorded

Permitted write scope: Plan:ledger/adoption/DesktopPlatform.md; Plan:ledger/tasks/ADOPT.02.md

Validation (P2-017; no macOS/hosted runtime, device, GUI, browser E2E, live-service, inference or installed-consumer CI): Review of merged source, retained CI results and receipts only; no new builds, downloads or runtime checks (P2-017).
Completion evidence for the ledger: Repository adoption record with the repository-wide facts, links to every slice record, the combined classification table and any conflicts raised under D-001.
```

```text
Execute ArcForges delivery task ADOPT.03 — Adopt Contracts.

Task record: C:\MyFile\Projects\ArcForges-Design-B\docs\planning\delivery\lanes\adoption.md (anchor task-adopt-03).
Delivery rules: C:\MyFile\Projects\ArcForges-Design-B\docs\planning\delivery\README.md; execution: C:\MyFile\Projects\Plan-B\arcforges-implementation.md.
Owning repository: C:\MyFile\Projects\ArcForges\Contracts (integration owner: Contracts integration owner).
Kind/size: adoption/S. Baseline: not-started.
Outcome: The repository-wide adoption facts for Contracts (main head, retained CI workflow inventory under P2-017, package identities and pins, shared roots and source inventory) are recorded once for its slices to cite, and the Contracts classification table is complete when every adoption slice of the repository is complete. The accepted WP-03.00 to WP-03.02 receipts are recorded as inherited by the contracts slice; every later Contracts task, starting with the WP-03.03 closures, is open.

Obligations (authoritative definitions; satisfy exactly these parts and their tests/gates):
- P2-018 (adoption stage: Contracts repository record): C:\MyFile\Projects\ArcForges-Design-B\docs\decisions\phase-2-specification-decisions.md, anchor rule-p2-018

Adoption slices (claim, review and record each separately as ledger/tasks/<slice>.md; one pull request may carry several; each slice opens only its own repository lane; see the Design adoption stage):
- ADOPT.03.contracts: Adopt Contracts: Contracts schema closures (opens 22 tasks; records 3 accepted tasks as inherited)
- ADOPT.03.extensions: Adopt Contracts: Extension platform and integrations (opens 3 tasks)
- ADOPT.03.governance: Adopt Contracts: Family governance and policy tests (opens 2 tasks)
- ADOPT.03.release: Adopt Contracts: Release readiness and family release (opens 1 task)

Start prerequisites (before claiming, each contract/artifact/design prerequisite must be delivered or complete and each release prerequisite complete in the Plan ledger; DLV-24):
- [artifact] ADOPT.01: frozen baseline record
Completion prerequisites (may start earlier; cannot complete before these are complete):
- [integration] ADOPT.03.contracts: slice recorded
- [integration] ADOPT.03.extensions: slice recorded
- [integration] ADOPT.03.governance: slice recorded
- [integration] ADOPT.03.release: slice recorded

Permitted write scope: Plan:ledger/adoption/Contracts.md; Plan:ledger/tasks/ADOPT.03.md

Validation (P2-017; no macOS/hosted runtime, device, GUI, browser E2E, live-service, inference or installed-consumer CI): Review of merged source, retained CI results and receipts only; no new builds, downloads or runtime checks (P2-017).
Completion evidence for the ledger: Repository adoption record with the repository-wide facts, links to every slice record, the combined classification table and any conflicts raised under D-001.
```

```text
Execute ArcForges delivery task ADOPT.04 — Adopt ArcNotes.

Task record: C:\MyFile\Projects\ArcForges-Design-B\docs\planning\delivery\lanes\adoption.md (anchor task-adopt-04).
Delivery rules: C:\MyFile\Projects\ArcForges-Design-B\docs\planning\delivery\README.md; execution: C:\MyFile\Projects\Plan-B\arcforges-implementation.md.
Owning repository: C:\MyFile\Projects\ArcForges\ArcNotes (integration owner: ArcNotes integration owner).
Kind/size: adoption/S. Baseline: not-started.
Outcome: The repository-wide adoption facts for ArcNotes (main head, retained CI workflow inventory under P2-017, package identities and pins, shared roots and source inventory) are recorded once for its slices to cite, and the ArcNotes classification table is complete when every adoption slice of the repository is complete.

Obligations (authoritative definitions; satisfy exactly these parts and their tests/gates):
- P2-018 (adoption stage: ArcNotes repository record): C:\MyFile\Projects\ArcForges-Design-B\docs\decisions\phase-2-specification-decisions.md, anchor rule-p2-018

Adoption slices (claim, review and record each separately as ledger/tasks/<slice>.md; one pull request may carry several; each slice opens only its own repository lane; see the Design adoption stage):
- ADOPT.04.app-composition: Adopt ArcNotes: Application composition (opens 2 tasks)
- ADOPT.04.arcnotes: Adopt ArcNotes: ArcNotes (opens 35 tasks)
- ADOPT.04.governance: Adopt ArcNotes: Family governance and policy tests (opens 1 task)
- ADOPT.04.release: Adopt ArcNotes: Release readiness and family release (opens 1 task)
- ADOPT.04.runtime-proofs: Adopt ArcNotes: Runtime proofs (opens 1 task)

Start prerequisites (before claiming, each contract/artifact/design prerequisite must be delivered or complete and each release prerequisite complete in the Plan ledger; DLV-24):
- [artifact] ADOPT.01: frozen baseline record
Completion prerequisites (may start earlier; cannot complete before these are complete):
- [integration] ADOPT.04.app-composition: slice recorded
- [integration] ADOPT.04.arcnotes: slice recorded
- [integration] ADOPT.04.governance: slice recorded
- [integration] ADOPT.04.release: slice recorded
- [integration] ADOPT.04.runtime-proofs: slice recorded

Permitted write scope: Plan:ledger/adoption/ArcNotes.md; Plan:ledger/tasks/ADOPT.04.md

Validation (P2-017; no macOS/hosted runtime, device, GUI, browser E2E, live-service, inference or installed-consumer CI): Review of merged source, retained CI results and receipts only; no new builds, downloads or runtime checks (P2-017).
Completion evidence for the ledger: Repository adoption record with the repository-wide facts, links to every slice record, the combined classification table and any conflicts raised under D-001.
```

```text
Execute ArcForges delivery task ADOPT.05 — Adopt ArcScope.

Task record: C:\MyFile\Projects\ArcForges-Design-B\docs\planning\delivery\lanes\adoption.md (anchor task-adopt-05).
Delivery rules: C:\MyFile\Projects\ArcForges-Design-B\docs\planning\delivery\README.md; execution: C:\MyFile\Projects\Plan-B\arcforges-implementation.md.
Owning repository: C:\MyFile\Projects\ArcForges\ArcScope (integration owner: ArcScope integration owner).
Kind/size: adoption/S. Baseline: not-started.
Outcome: The repository-wide adoption facts for ArcScope (main head, retained CI workflow inventory under P2-017, package identities and pins, shared roots and source inventory) are recorded once for its slices to cite, and the ArcScope classification table is complete when every adoption slice of the repository is complete.

Obligations (authoritative definitions; satisfy exactly these parts and their tests/gates):
- P2-018 (adoption stage: ArcScope repository record): C:\MyFile\Projects\ArcForges-Design-B\docs\decisions\phase-2-specification-decisions.md, anchor rule-p2-018

Adoption slices (claim, review and record each separately as ledger/tasks/<slice>.md; one pull request may carry several; each slice opens only its own repository lane; see the Design adoption stage):
- ADOPT.05.arcscope: Adopt ArcScope: ArcScope (opens 27 tasks)
- ADOPT.05.governance: Adopt ArcScope: Family governance and policy tests (opens 1 task)
- ADOPT.05.release: Adopt ArcScope: Release readiness and family release (opens 1 task)
- ADOPT.05.runtime-proofs: Adopt ArcScope: Runtime proofs (opens 1 task)
- ADOPT.05.simulator: Adopt ArcScope: ArcScope Cloud simulator (opens 1 task)

Start prerequisites (before claiming, each contract/artifact/design prerequisite must be delivered or complete and each release prerequisite complete in the Plan ledger; DLV-24):
- [artifact] ADOPT.01: frozen baseline record
Completion prerequisites (may start earlier; cannot complete before these are complete):
- [integration] ADOPT.05.arcscope: slice recorded
- [integration] ADOPT.05.governance: slice recorded
- [integration] ADOPT.05.release: slice recorded
- [integration] ADOPT.05.runtime-proofs: slice recorded
- [integration] ADOPT.05.simulator: slice recorded

Permitted write scope: Plan:ledger/adoption/ArcScope.md; Plan:ledger/tasks/ADOPT.05.md

Validation (P2-017; no macOS/hosted runtime, device, GUI, browser E2E, live-service, inference or installed-consumer CI): Review of merged source, retained CI results and receipts only; no new builds, downloads or runtime checks (P2-017).
Completion evidence for the ledger: Repository adoption record with the repository-wide facts, links to every slice record, the combined classification table and any conflicts raised under D-001.
```

```text
Execute ArcForges delivery task ADOPT.06 — Adopt ArcSlate.

Task record: C:\MyFile\Projects\ArcForges-Design-B\docs\planning\delivery\lanes\adoption.md (anchor task-adopt-06).
Delivery rules: C:\MyFile\Projects\ArcForges-Design-B\docs\planning\delivery\README.md; execution: C:\MyFile\Projects\Plan-B\arcforges-implementation.md.
Owning repository: C:\MyFile\Projects\ArcForges\ArcSlate (integration owner: ArcSlate integration owner).
Kind/size: adoption/S. Baseline: not-started.
Outcome: The repository-wide adoption facts for ArcSlate (main head, retained CI workflow inventory under P2-017, package identities and pins, shared roots and source inventory) are recorded once for its slices to cite, and the ArcSlate classification table is complete when every adoption slice of the repository is complete.

Obligations (authoritative definitions; satisfy exactly these parts and their tests/gates):
- P2-018 (adoption stage: ArcSlate repository record): C:\MyFile\Projects\ArcForges-Design-B\docs\decisions\phase-2-specification-decisions.md, anchor rule-p2-018

Adoption slices (claim, review and record each separately as ledger/tasks/<slice>.md; one pull request may carry several; each slice opens only its own repository lane; see the Design adoption stage):
- ADOPT.06.arcslate: Adopt ArcSlate: ArcSlate (opens 41 tasks)
- ADOPT.06.governance: Adopt ArcSlate: Family governance and policy tests (opens 1 task)
- ADOPT.06.release: Adopt ArcSlate: Release readiness and family release (opens 1 task)
- ADOPT.06.runtime-proofs: Adopt ArcSlate: Runtime proofs (opens 1 task)

Start prerequisites (before claiming, each contract/artifact/design prerequisite must be delivered or complete and each release prerequisite complete in the Plan ledger; DLV-24):
- [artifact] ADOPT.01: frozen baseline record
Completion prerequisites (may start earlier; cannot complete before these are complete):
- [integration] ADOPT.06.arcslate: slice recorded
- [integration] ADOPT.06.governance: slice recorded
- [integration] ADOPT.06.release: slice recorded
- [integration] ADOPT.06.runtime-proofs: slice recorded

Permitted write scope: Plan:ledger/adoption/ArcSlate.md; Plan:ledger/tasks/ADOPT.06.md

Validation (P2-017; no macOS/hosted runtime, device, GUI, browser E2E, live-service, inference or installed-consumer CI): Review of merged source, retained CI results and receipts only; no new builds, downloads or runtime checks (P2-017).
Completion evidence for the ledger: Repository adoption record with the repository-wide facts, links to every slice record, the combined classification table and any conflicts raised under D-001.
```

```text
Execute ArcForges delivery task ADOPT.07 — Adopt Cloud.

Task record: C:\MyFile\Projects\ArcForges-Design-B\docs\planning\delivery\lanes\adoption.md (anchor task-adopt-07).
Delivery rules: C:\MyFile\Projects\ArcForges-Design-B\docs\planning\delivery\README.md; execution: C:\MyFile\Projects\Plan-B\arcforges-implementation.md.
Owning repository: C:\MyFile\Projects\ArcForges\Cloud (integration owner: Cloud integration owner).
Kind/size: adoption/S. Baseline: not-started.
Outcome: The repository-wide adoption facts for Cloud (main head, retained CI workflow inventory under P2-017, package identities and pins, shared roots and source inventory) are recorded once for its slices to cite, and the Cloud classification table is complete when every adoption slice of the repository is complete.

Obligations (authoritative definitions; satisfy exactly these parts and their tests/gates):
- P2-018 (adoption stage: Cloud repository record): C:\MyFile\Projects\ArcForges-Design-B\docs\decisions\phase-2-specification-decisions.md, anchor rule-p2-018

Adoption slices (claim, review and record each separately as ledger/tasks/<slice>.md; one pull request may carry several; each slice opens only its own repository lane; see the Design adoption stage):
- ADOPT.07.ai-routing: Adopt Cloud: Workers AI routing and metering (opens 6 tasks)
- ADOPT.07.cloud: Adopt Cloud: Cloud core (opens 58 tasks)
- ADOPT.07.commerce: Adopt Cloud: Commerce, entitlement and credits (opens 15 tasks)
- ADOPT.07.device-bridge: Adopt Cloud: Application presence and tool bridge (opens 9 tasks)
- ADOPT.07.extensions: Adopt Cloud: Extension platform and integrations (opens 1 task)
- ADOPT.07.governance: Adopt Cloud: Family governance and policy tests (opens 1 task)
- ADOPT.07.harness: Adopt Cloud: Cloud Harness (opens 2 tasks)
- ADOPT.07.operations: Adopt Cloud: Operations, support and trust and safety (opens 9 tasks)
- ADOPT.07.policy: Adopt Cloud: Dynamic policy and configuration (opens 10 tasks)
- ADOPT.07.release: Adopt Cloud: Release readiness and family release (opens 3 tasks)
- ADOPT.07.runtime-proofs: Adopt Cloud: Runtime proofs (opens 1 task)
- ADOPT.07.search: Adopt Cloud: Knowledge search and retrieval (opens 8 tasks)
- ADOPT.07.simulator: Adopt Cloud: ArcScope Cloud simulator (opens 9 tasks)

Start prerequisites (before claiming, each contract/artifact/design prerequisite must be delivered or complete and each release prerequisite complete in the Plan ledger; DLV-24):
- [artifact] ADOPT.01: frozen baseline record
Completion prerequisites (may start earlier; cannot complete before these are complete):
- [integration] ADOPT.07.ai-routing: slice recorded
- [integration] ADOPT.07.cloud: slice recorded
- [integration] ADOPT.07.commerce: slice recorded
- [integration] ADOPT.07.device-bridge: slice recorded
- [integration] ADOPT.07.extensions: slice recorded
- [integration] ADOPT.07.governance: slice recorded
- [integration] ADOPT.07.harness: slice recorded
- [integration] ADOPT.07.operations: slice recorded
- [integration] ADOPT.07.policy: slice recorded
- [integration] ADOPT.07.release: slice recorded
- [integration] ADOPT.07.runtime-proofs: slice recorded
- [integration] ADOPT.07.search: slice recorded
- [integration] ADOPT.07.simulator: slice recorded

Permitted write scope: Plan:ledger/adoption/Cloud.md; Plan:ledger/tasks/ADOPT.07.md

Validation (P2-017; no macOS/hosted runtime, device, GUI, browser E2E, live-service, inference or installed-consumer CI): Review of merged source, retained CI results and receipts only; no new builds, downloads or runtime checks (P2-017).
Completion evidence for the ledger: Repository adoption record with the repository-wide facts, links to every slice record, the combined classification table and any conflicts raised under D-001.
```

```text
Execute ArcForges delivery task ADOPT.08 — Adopt AI.

Task record: C:\MyFile\Projects\ArcForges-Design-B\docs\planning\delivery\lanes\adoption.md (anchor task-adopt-08).
Delivery rules: C:\MyFile\Projects\ArcForges-Design-B\docs\planning\delivery\README.md; execution: C:\MyFile\Projects\Plan-B\arcforges-implementation.md.
Owning repository: C:\MyFile\Projects\ArcForges\AI (integration owner: AI integration owner).
Kind/size: adoption/S. Baseline: not-started.
Outcome: The repository-wide adoption facts for AI (main head, retained CI workflow inventory under P2-017, package identities and pins, shared roots and source inventory) are recorded once for its slices to cite, and the AI classification table is complete when every adoption slice of the repository is complete.

Obligations (authoritative definitions; satisfy exactly these parts and their tests/gates):
- P2-018 (adoption stage: AI repository record): C:\MyFile\Projects\ArcForges-Design-B\docs\decisions\phase-2-specification-decisions.md, anchor rule-p2-018

Adoption slices (claim, review and record each separately as ledger/tasks/<slice>.md; one pull request may carry several; each slice opens only its own repository lane; see the Design adoption stage):
- ADOPT.08.ai-routing: Adopt AI: Workers AI routing and metering (opens 5 tasks)
- ADOPT.08.extensions: Adopt AI: Extension platform and integrations (opens 1 task)
- ADOPT.08.governance: Adopt AI: Family governance and policy tests (opens 1 task)
- ADOPT.08.harness: Adopt AI: Cloud Harness (opens 7 tasks)

Start prerequisites (before claiming, each contract/artifact/design prerequisite must be delivered or complete and each release prerequisite complete in the Plan ledger; DLV-24):
- [artifact] ADOPT.01: frozen baseline record
Completion prerequisites (may start earlier; cannot complete before these are complete):
- [integration] ADOPT.08.ai-routing: slice recorded
- [integration] ADOPT.08.extensions: slice recorded
- [integration] ADOPT.08.governance: slice recorded
- [integration] ADOPT.08.harness: slice recorded

Permitted write scope: Plan:ledger/adoption/AI.md; Plan:ledger/tasks/ADOPT.08.md

Validation (P2-017; no macOS/hosted runtime, device, GUI, browser E2E, live-service, inference or installed-consumer CI): Review of merged source, retained CI results and receipts only; no new builds, downloads or runtime checks (P2-017).
Completion evidence for the ledger: Repository adoption record with the repository-wide facts, links to every slice record, the combined classification table and any conflicts raised under D-001.
```

```text
Execute ArcForges delivery task ADOPT.09 — Adopt Web.

Task record: C:\MyFile\Projects\ArcForges-Design-B\docs\planning\delivery\lanes\adoption.md (anchor task-adopt-09).
Delivery rules: C:\MyFile\Projects\ArcForges-Design-B\docs\planning\delivery\README.md; execution: C:\MyFile\Projects\Plan-B\arcforges-implementation.md.
Owning repository: C:\MyFile\Projects\ArcForges\Web (integration owner: Web integration owner).
Kind/size: adoption/S. Baseline: not-started.
Outcome: The repository-wide adoption facts for Web (main head, retained CI workflow inventory under P2-017, package identities and pins, shared roots and source inventory) are recorded once for its slices to cite, and the Web classification table is complete when every adoption slice of the repository is complete.

Obligations (authoritative definitions; satisfy exactly these parts and their tests/gates):
- P2-018 (adoption stage: Web repository record): C:\MyFile\Projects\ArcForges-Design-B\docs\decisions\phase-2-specification-decisions.md, anchor rule-p2-018

Adoption slices (claim, review and record each separately as ledger/tasks/<slice>.md; one pull request may carry several; each slice opens only its own repository lane; see the Design adoption stage):
- ADOPT.09.governance: Adopt Web: Family governance and policy tests (opens 1 task)
- ADOPT.09.operations: Adopt Web: Operations, support and trust and safety (opens 4 tasks)
- ADOPT.09.release: Adopt Web: Release readiness and family release (opens 1 task)
- ADOPT.09.runtime-proofs: Adopt Web: Runtime proofs (opens 1 task)
- ADOPT.09.web: Adopt Web: Web (opens 31 tasks)

Start prerequisites (before claiming, each contract/artifact/design prerequisite must be delivered or complete and each release prerequisite complete in the Plan ledger; DLV-24):
- [artifact] ADOPT.01: frozen baseline record
Completion prerequisites (may start earlier; cannot complete before these are complete):
- [integration] ADOPT.09.governance: slice recorded
- [integration] ADOPT.09.operations: slice recorded
- [integration] ADOPT.09.release: slice recorded
- [integration] ADOPT.09.runtime-proofs: slice recorded
- [integration] ADOPT.09.web: slice recorded

Permitted write scope: Plan:ledger/adoption/Web.md; Plan:ledger/tasks/ADOPT.09.md

Validation (P2-017; no macOS/hosted runtime, device, GUI, browser E2E, live-service, inference or installed-consumer CI): Review of merged source, retained CI results and receipts only; no new builds, downloads or runtime checks (P2-017).
Completion evidence for the ledger: Repository adoption record with the repository-wide facts, links to every slice record, the combined classification table and any conflicts raised under D-001.
```

```text
Execute ArcForges delivery task ADOPT.10 — Adopt Mobile.

Task record: C:\MyFile\Projects\ArcForges-Design-B\docs\planning\delivery\lanes\adoption.md (anchor task-adopt-10).
Delivery rules: C:\MyFile\Projects\ArcForges-Design-B\docs\planning\delivery\README.md; execution: C:\MyFile\Projects\Plan-B\arcforges-implementation.md.
Owning repository: C:\MyFile\Projects\ArcForges\Mobile (integration owner: Mobile integration owner).
Kind/size: adoption/S. Baseline: not-started.
Outcome: The repository-wide adoption facts for Mobile (main head, retained CI workflow inventory under P2-017, package identities and pins, shared roots and source inventory) are recorded once for its slices to cite, and the Mobile classification table is complete when every adoption slice of the repository is complete.

Obligations (authoritative definitions; satisfy exactly these parts and their tests/gates):
- P2-018 (adoption stage: Mobile repository record): C:\MyFile\Projects\ArcForges-Design-B\docs\decisions\phase-2-specification-decisions.md, anchor rule-p2-018

Adoption slices (claim, review and record each separately as ledger/tasks/<slice>.md; one pull request may carry several; each slice opens only its own repository lane; see the Design adoption stage):
- ADOPT.10.android: Adopt Mobile: Android companion (opens 26 tasks)
- ADOPT.10.governance: Adopt Mobile: Family governance and policy tests (opens 1 task)
- ADOPT.10.release: Adopt Mobile: Release readiness and family release (opens 1 task)
- ADOPT.10.runtime-proofs: Adopt Mobile: Runtime proofs (opens 1 task)

Start prerequisites (before claiming, each contract/artifact/design prerequisite must be delivered or complete and each release prerequisite complete in the Plan ledger; DLV-24):
- [artifact] ADOPT.01: frozen baseline record
Completion prerequisites (may start earlier; cannot complete before these are complete):
- [integration] ADOPT.10.android: slice recorded
- [integration] ADOPT.10.governance: slice recorded
- [integration] ADOPT.10.release: slice recorded
- [integration] ADOPT.10.runtime-proofs: slice recorded

Permitted write scope: Plan:ledger/adoption/Mobile.md; Plan:ledger/tasks/ADOPT.10.md

Validation (P2-017; no macOS/hosted runtime, device, GUI, browser E2E, live-service, inference or installed-consumer CI): Review of merged source, retained CI results and receipts only; no new builds, downloads or runtime checks (P2-017).
Completion evidence for the ledger: Repository adoption record with the repository-wide facts, links to every slice record, the combined classification table and any conflicts raised under D-001.
```

```text
Execute ArcForges delivery task ADOPT.11 — Reconcile Design and Plan documentation for adoption.

Task record: C:\MyFile\Projects\ArcForges-Design-B\docs\planning\delivery\lanes\adoption.md (anchor task-adopt-11).
Delivery rules: C:\MyFile\Projects\ArcForges-Design-B\docs\planning\delivery\README.md; execution: C:\MyFile\Projects\Plan-B\arcforges-implementation.md.
Owning repository: C:\MyFile\Projects\ArcForges-Design-B (integration owner: Design integration owner). Also touches: Plan.
Kind/size: adoption/S. Baseline: not-started.
Outcome: Documentation findings that affect adoption decisions are resolved or scheduled (including the pre-existing corpus citation drift recorded in the adoption stage document), the generated views are confirmed current, and the ledger shows which adoption slices are complete.

Obligations (authoritative definitions; satisfy exactly these parts and their tests/gates):
- P2-018 (adoption stage: documentation reconciliation): C:\MyFile\Projects\ArcForges-Design-B\docs\decisions\phase-2-specification-decisions.md, anchor rule-p2-018

Start prerequisites (before claiming, each contract/artifact/design prerequisite must be delivered or complete and each release prerequisite complete in the Plan ledger; DLV-24):
- [artifact] ADOPT.01: frozen baseline record
Completion prerequisites (may start earlier; cannot complete before these are complete):
- none

Permitted write scope: Design:docs/**; Plan:ledger/adoption/documentation.md

Validation (P2-017; no macOS/hosted runtime, device, GUI, browser E2E, live-service, inference or installed-consumer CI): Documentation consistency and link review, delivery graph check and the existing corpus integrity check; no product builds (P2-017).
Completion evidence for the ledger: Reconciliation record with checker results and any planning-change pull requests.
```
