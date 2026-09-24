# Execution ledger

The ledger records the execution state of delivery tasks. Together with the Design delivery graph it determines readiness (`python tools/delivery.py ready`). It holds no design authority: task definitions, prerequisites and obligations live in the Design graph.

## Claims

Claims are branches, not files on `main`. `claims/<task-id>` (lower case) is created atomically by the claimant for a task or an adoption slice (for example `claims/adopt.03.contracts`); its commits hold a `claim.json` with `task`, `claimant`, `claimedAt`, `leaseUntil`, `epoch` and `state` (`claimed`, `blocked`, `released`, `delivered` or `complete`). Renewal appends a commit with the same epoch; re-claim of a released task and recovery takeover append a commit with the next epoch, and only the claimant at the current epoch may have the task's pull requests merged. Exclusive resource leases use `leases/<resource-id>` branches with the same record and rules. Claim branches are never deleted or force-updated; they are the audit trail of ownership. Repository administrators may add a ruleset that blocks deletion and non-fast-forward updates of `claims/*` and `leases/*`.

## Task records

One file per task, `ledger/tasks/<TASK-ID>.md`, added through a reviewed pull request:

```markdown
---
task: CON.02
status: complete
recorded: 2026-10-01
claimant: worker-name
---

## Evidence
- Pull requests and merge commits:
- Published candidate identities (package, version, hash, registry receipt):
- Obligations satisfied (substep or package obligation and part):
- Validation actually performed (CI checks, local runtime checks with environment identity):
- Substitutes still in use and their removing tasks:
- Untested coverage:
```

`status` is one of `delivered` (outcome merged and published, a completion prerequisite still open), `complete`, `inherited` (satisfied by reviewed existing work during adoption) or `superseded` (replaced by a recorded planning change). Keep exactly one front-matter block per file: when a task moves from `delivered` to `complete`, or is superseded, edit the existing header in place and append the new evidence below it; do not add a second header block.

## Adoption records

`ledger/adoption/baseline.md` holds the frozen adoption inputs. Each adoption slice is recorded as `ledger/tasks/ADOPT.NN.<lane>.md` (for example `ledger/tasks/ADOPT.03.contracts.md`) with `status: complete` and one classification row per task in its scope; the tasks of that lane in that repository become ready when the record is merged. `ledger/adoption/<repository>.md` holds each repository's facts and combined classification table, and `ledger/tasks/ADOPT.NN.md` records the repository adoption task when all of its slices are complete. Their format and rules are defined in the Design [adoption stage](https://github.com/ArcForges/ArcForges-Design-B/blob/main/docs/planning/delivery/adoption.md). No adoption record exists yet: the adoption stage has not been executed. The baseline is complete through WP03.02; WP03.03 has not started.
