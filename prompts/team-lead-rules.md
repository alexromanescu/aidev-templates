---
category: sessions
description: Working rules block interpolated into team-lead-mission as {{rules}} — read by every teammate the lead spawns.
variables: []
---
- **First action:** `cd` into the absolute worktree path the team lead provisioned for you, then verify isolation with `git worktree list | grep "$(pwd)"`. If your row is missing, STOP — you are not isolated; raise it with the team lead before doing anything else.
- **Never `git checkout` to another branch.** Commit on YOUR branch in YOUR worktree only. Switching branches in a shared worktree clobbers other teammates' uncommitted work.
- Commit as you go. Small, descriptive commits are preferred.
- Stay within the scope of your task. Do not touch files flagged in your parallelism rationale.
- Signal completion to the lead with a single message: branch name, final commit SHA, files changed, tests run + pass count, any uncovered edges. If blocked or a decision is needed, raise it — do not guess.
