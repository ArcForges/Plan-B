# Task commands

Use one of these commands to start a worker. Each worker owns one claimed task (or one bundle of compatible ready tasks) at a time; several workers may run at once, including in the same repository.

## Execute a specific task

```text
Execute ArcForges delivery task <TASK-ID>. Read C:\MyFile\Projects\Plan-B\arcforges-implementation.md completely and follow it, including execution-policy.md, within the scope authorized by the user. Confirm with `python tools/delivery.py ready --claims` that the task is ready and unclaimed, then claim it atomically. Take its self-contained prompt from the lane file under C:\MyFile\Projects\Plan-B\tasks\ and its record from C:\MyFile\Projects\ArcForges-Design-B\docs\planning\delivery\lanes\.
Verify relevant facts, finish research and decisions, then establish one complete ordered plan before editing. Execute continuously in a retained worktree of the owning repository; append to the task's open PR or create one titled [<TASK-ID>] ... Repair authoritative documentation conflicts through Design pull requests.
No macOS CI, hosted device/emulator/GUI/browser E2E, live service/inference, installed-consumer or public-release upgrade tests. No routine public artifact downloads, repeated archive/hash comparison or post-merge runtime cycles. Keep necessary Windows/Linux compilation/AOT/packaging, targeted offline/static/security checks and required signing/licence/lock integrity. Runtime tests are affected-scope local opt-in using existing environments, once; no validation-driven toolchain reinstall; one CPU-heavy local build per workstation.
Use normal networking, no proxy7890 and no wsl.exe wrappers. On a network failure, stop and report the operation. Do not create tags or republish solely to verify.
Review every PR and fix findings. Merge after retained applicable CI is green; docs-only PRs without CI merge after review. Record the task in the Plan ledger, renew or finalize the claim, keep branches/worktrees and report actual results and untested coverage. The user's latest instructions determine whether to start, continue or stop.
```

## Take the next ready task in a lane

```text
Act as an ArcForges delivery worker for lane <lane>. Read C:\MyFile\Projects\Plan-B\arcforges-implementation.md completely. Run `python tools/delivery.py ready --claims --lane <lane>`, choose the ready task that is on the critical path or unblocks the most work, claim it atomically, and execute it exactly as the "Execute a specific task" command describes. When it is complete and recorded, repeat while the user's instruction allows.
```

## Run one adoption slice

```text
Execute ArcForges adoption slice <ADOPT.NN.lane> (repository <repository>, lane <lane>). Read C:\MyFile\Projects\Plan-B\arcforges-implementation.md and C:\MyFile\Projects\ArcForges-Design-B\docs\planning\delivery\adoption.md completely. Confirm with `python tools/delivery.py ready --claims` that the slice is ready and unclaimed, then claim it atomically. Classify every delivery task of that lane in that repository as inherited, inherited with adjustment, gap or conflicting under ADP-01 to ADP-08, using only reviewed evidence (the baseline is complete through WP03.02; WP03.03 has not started). Record the slice as ledger/tasks/<ADOPT.NN.lane>.md and any inherited-task records in the Plan ledger; raise conflicts under D-001; propose planning changes for adjustments that do not fit existing tasks. Several slices may share one reviewed pull request. Do not execute implementation tasks during adoption.
```
