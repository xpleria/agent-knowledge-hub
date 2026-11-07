# Orchestrator: brief, sequence, verify, report

- **Scope:** How does an orchestrator brief, sequence, verify and report on delegated work so the owner gets verified results and no agent overwrites another?
- **Keywords:** orchestrator, delegation, subagent brief, steer, one writer per tree, self-report, verification, continuation, denied command, deploy order, owner question, standing list, verbatim, acceptance
- **Status:** current
- **Updated:** 2026-11-07
- **Sources:** distilled from a Godot project's orchestration lessons and agent role lessons; see also `practices/delegation-briefs.md`

## Delegate and sequence

- Delegate investigation, implementation, commits and documentation. Verify only what gates the next step; your context is the scarcest resource.
- Run one writing agent per working tree at a time. Read-only research may run alongside.
- Cap a run at about three related items, and chain runs with an explicit order. Long runs stall, lose their thread or stop early.
- Commit before every deploy, when commits are permitted, and deploy one batch at a time, so the owner can see what each item did.
- Push only when the owner says so, and only after the implementer has finished. Never force-push.
- Owner approval is scoped to the slice that was reviewed. Deploy one slice, pause, and wait. Approval of one slice does not authorise the next, and a "looks good" on one device or screen verifies only the surface that was shown.

## Brief every subagent

- Give the repo path, branch, skills to load, hard rules, the owner's words verbatim (a brief is transient), the item order and the report format.
- Restate the no-discard rule in every brief. Weak agents reach for `git checkout` to undo experiments.
- Give precise success criteria and demand an honest "not done" report.
- Send new owner feedback to a running agent by steering it, not by starting a second writer.

## Verify before relaying

- Treat every subagent report as a self-report. Check any claim that gates the next step with evidence: `git log`, `git status`, `git diff`, a hash comparison, or test output.
- Expect smaller-model subagents to stop early or over-claim. Verify landed work each time, whatever the report says.
- After a short or partial stop, dispatch a continuation. Its step 0 is `git status` and the log since the base. It returns a table of each claimed item with its commit or grep evidence.
- Never relay a prior "done" without that evidence.

## Handle denials and protected files

- If a subagent's command is denied, it stops and reports the exact command, its purpose and why it is safe. The orchestrator verifies that, then runs the command itself so the owner sees the approval prompt.
- Auto-denied patterns (these stop a run without an approval prompt): heredocs, inline interpreters (`python -c`, `node -e`, `bash -c`), bulk in-place rewrites (`sed -i`, `perl -pi`), recursive deletes (`rm -rf`), and an edit chained to a run.
- Workaround: edit with the file tools (read, patch, write). Before a risky edit, copy the file to a backup; to undo, copy the backup back and confirm with `cmp` that the two are identical. Never undo with `git checkout`.
- Protected instruction files are edited by the orchestrator, after the running implementer has finished, and only when the owner has approved. A denied write is not retried by another route.

## Route owner input

- Put each owner question as: decision, context, options with their impact, recommended option first. Batch independent questions.
- Do not ask what the plan already recommends. Flag a stale premise when the code has already superseded it.
- Keep a standing list split into: accepted, awaiting owner check, blocked on an answer, queued.
