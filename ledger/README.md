# Execution ledger

The ledger records the execution state of delivery tasks. Together with the Design delivery graph it determines readiness (`python tools/delivery.py ready`). It holds no design authority: task definitions, prerequisites and obligations live in the Design graph.

## Claims

Claims are branches, not files on `main`. `claims/<task-id>` (lower case) is created atomically by the claimant; its commits hold a `claim.json` with `task`, `claimant`, `claimedAt`, `leaseUntil` and `state` (`claimed`, `blocked`, `released`, `delivered` or `complete`). Renewal, re-claim of a released task and takeover after lease expiry append fast-forward commits to the same branch. Claim branches are never deleted or force-updated; they are the audit trail of ownership. Repository administrators may add a ruleset that blocks deletion and non-fast-forward updates of `claims/*`.

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

`ledger/adoption/baseline.md` holds the frozen adoption inputs, and `ledger/adoption/<repository>.md` holds each repository's classification table. Their format and rules are defined in the Design [adoption stage](https://github.com/ArcForges/ArcForges-Design-B/blob/main/docs/planning/delivery/adoption.md). No adoption record exists yet: the adoption stage has not been executed.
