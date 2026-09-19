---
name: task-isolation
description: Choose a safe Git isolation level for a development task. Use a focused branch by default and a worktree when parallel agents, parallel sessions, or risky isolation justify it.
---

# Task isolation

## Default

For meaningful work, create a focused branch from the current accepted base.

Do not work directly on the protected/default branch unless Emmanuel explicitly chooses that path.

## Use a normal branch when

- one agent/session is working;
- the current checkout is clean and available;
- no parallel task needs the same working tree;
- the task has ordinary risk.

## Use a worktree when

- multiple agents or sessions need the repository concurrently;
- two tasks must remain independently runnable;
- a risky experiment should not disturb the primary checkout;
- parallel review/testing needs separate revisions.

Worktrees are a tool, not a ceremony.

## Before starting

1. Fetch the current remote state.
2. Inspect current branch and uncommitted work.
3. Check whether another task or PR touches the same files when parallel work is active.
4. Preserve unrelated work.
5. Name the branch for the task.

## Safety

- Never reuse another agent's active branch/worktree.
- Never discard unrelated uncommitted work.
- Do not use plain force push.
- Shared databases, ports, credentials, and cloud resources are not isolated by Git.
- Do not run destructive schema/data experiments against shared production resources.

## Finish

Keep the branch/worktree until the work is reviewed or deliberately abandoned. Cleanup is a separate action after merge/closure.
