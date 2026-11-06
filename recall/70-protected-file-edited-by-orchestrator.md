# Protected file edited by the orchestrator

- **Scope:** Who edits a protected instruction file such as the project's AGENTS.md, and what happens when a subagent's write is refused?
- **Keywords:** protected file, AGENTS.md, instruction file, approval, write refused, orchestrator, implementer, owner prompt
- **Status:** current
- **Updated:** 2026-11-01
- **Source project:** ganvchi-court

## What happened

An implementer needed one sentence changed in the project's instruction file. Its write was
refused by the approval layer. The implementer then tried to make the same edit through
another tool, which the refusal forbids.

## Lesson

- Subagents do not edit protected instruction files.
- The implementer reports the exact change it needs: file, sentence, old text, new text, reason.
- The orchestrator edits the file itself, after the running implementer has finished, so the owner sees the approval prompt.
- A refused write is never retried through another route. Report it and wait for the owner's decision.

## Why

The approval prompt is the owner's control over the rules agents follow. Another route
bypasses it.
