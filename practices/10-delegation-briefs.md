# Delegation briefs

- **Scope:** What must a brief to a delegated agent contain so it can finish the job without guessing and without overclaiming?
- **Keywords:** brief, delegation, subagent, self-contained, success criteria, hard rules, verbatim, report format, item order, not done, steer
- **Status:** current
- **Sources:** distilled from a Godot project's orchestration runs (ganvchi-court)

A brief is the only context a delegated agent gets. Make it complete.

## Contents

1. **Location:** the exact repository path and branch. Never assume a path; discover it first.
2. **Skills and pages to read first:** name them, so the brief need not repeat them.
3. **Hard rules:** restate the project's no-discard and one-writer rules and any protected files.
4. **The owner's words, verbatim:** quote them in quotation marks. Do not paraphrase a requirement.
5. **Scope and order:** the items, in order, and what is out of scope.
6. **Success criteria:** the observable result that proves each item done, for example a test name that must pass or a hash that must match.
7. **Stop rules:** when to stop and report instead of working around a denial or a failure.
8. **Report format:** a table of each claimed item with its commit or evidence, plus a "not done" section.

## Rules

- Keep a run to about three related items. Chain runs with an explicit order.
- Name the files each agent may touch, so parallel agents do not collide.
- Tell the agent that a partial report with evidence is better than a complete-looking one without it.
- When the owner adds something mid-run, steer the running agent. Do not start a second agent in the same tree.
- Avoid recursive delete commands and long chained one-liners in a brief; they are often denied and stop the run.

## Why

Subagents that lack context stop early, or report "done" for work they did not verify.
A complete brief with explicit evidence rules is the cheapest prevention.
