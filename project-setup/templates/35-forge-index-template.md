# Forge topic index: <Topic name>

- **Scope:** What is this workstream's goal and scope, and which file answers which question?
- **Keywords:** <topic slug>, forge, index, goal, scope, status, reading guide, map
- **Status:** <forge: active | paused | blocked>
- **Updated:** <YYYY-MM-DD>
- **Sources:** <the playbook, plan and progress files in this folder>
- **Sign-off:** <commenced | accepted | partly accepted | deferred | cancelled> by the owner on <YYYY-MM-DD>; reference: <message id, link, commit or PR>; <qualifier, or none>

## Goal

<One short paragraph: the result the owner signed off to commence.>

## Scope

<What is in this topic, and what is out.>

## Status

<One line: the stage and the next step. Full state: `30-<slug>-progress.md`.>

## Reading guide

- <"Read the progress file first for the current state.">
- <"Read the plan for the stages and their acceptance checks.">

## Map

| File | What question it answers |
| --- | --- |
| [30-<slug>-progress.md](30-<slug>-progress.md) | What is verified, what is broken, and what is next? |
| [40-<slug>-<kind>.md](40-<slug>-<kind>.md) | <The question this file answers. One row per 40+ file.> |
| [99-<slug>-evidence/](99-<slug>-evidence/) | <What the evidence shows, if any evidence is kept.> |

Keep this index free of substance beyond the goal, scope, status line, reading guide and map.
Delete a map row that has no file behind it, and add one in the same change that adds a file.
