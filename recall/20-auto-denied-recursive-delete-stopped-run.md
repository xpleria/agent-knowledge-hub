# Auto-denied recursive delete stopped a delegated run

- **Scope:** Why did a delegated run stop when it tried a recursive delete, and what should a brief say instead?
- **Keywords:** rm -rf, recursive delete, denied, approval, auto-deny, screenshots, cleanup, brief, stop
- **Status:** current
- **Updated:** 2026-11-01
- **Source project:** ganvchi-court

## What happened

A subagent tried to clear an old screenshot folder with a recursive delete. The approval
layer denied it without asking the owner, and the run stopped mid-item. The denial read
as a user refusal, which it was not.

## Lesson

- Never put `rm -rf` or any recursive delete in a delegated brief or a subagent's plan.
- Write each capture to a new, uniquely named folder, so no cleanup is needed.
- Remove a single file with a plain `rm <file>`, one command per call.
- Remove a git worktree with `git worktree remove`.
- If a command is denied, stop and report the exact command, its purpose and why it is safe. The orchestrator then runs it so the owner sees the prompt.

## Why

Denied commands are not surfaced to the owner from inside a subagent. Working around the
denial bypasses the owner's decision, and stopping silently wastes the run.
