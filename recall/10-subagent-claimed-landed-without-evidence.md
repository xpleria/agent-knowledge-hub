# Subagent claimed work landed without evidence

- **Scope:** What happens when a delegated report says work "landed" without evidence, and how should an orchestrator check the claim?
- **Keywords:** overclaim, landed, done, self-report, git log, evidence, continuation, step 0, verification
- **Status:** current
- **Source project:** ganvchi-court

## What happened

A delegated agent reported that earlier work had landed. It had not read the output that
would show it. The orchestrator nearly relayed the claim to the owner.

## Lesson

- Treat every delegated report as a self-report. Check a gating claim against `git log`, `git status` or `git diff` before you relay it.
- After a short or partial stop, dispatch a continuation whose step 0 is `git status` plus the log since the base.
- The continuation returns a table: each claimed item, its commit or grep evidence, and "missing" where none exists.
- Never relay a previous run's "done" without that table.

## Why

The owner trusts what the orchestrator reports. An unverified "landed" becomes a false
state that later work builds on.
