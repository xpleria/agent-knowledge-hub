# agent-docs

- **Scope:** What does the work-lifecycle tree hold, and how does an agent move through it?
- **Keywords:** agent-docs, lore, forge, horizon, chronicle, lifecycle, work tracking, progress, index, sign-off, transitions
- **Status:** current
- **Updated:** 2026-11-07
- **Sources:** the project's `docs/README.md`, section "Documentation conventions"; the hub's `project-setup/31-sign-off-rules.md` and `project-setup/32-transitions.md`

This tree holds the work lifecycle of this project: what is in progress, what may come
later, and the lessons learned along the way. Settled facts live in
[`../docs/README.md`](../docs/README.md). `agent-docs/` may link into `docs/`; `docs/`
never links back.

## Stages

| Folder | What it holds |
| --- | --- |
| [`01-lore/`](01-lore/00-lore-index.md) | Lessons, rationale and pitfalls from finished or cancelled work, by subject. A living record. |
| [`02-forge/`](02-forge/00-forge-index.md) | Active work, one topic folder per workstream. |
| [`03-horizon/`](03-horizon/00-horizon-index.md) | Future work the owner has not committed to plan yet. |
| [`04-chronicle/`](04-chronicle/00-chronicle-index.md) | Thin register: one page per closed forge topic, with its closed date, sign-off, where its facts and lessons went, deferred links and one commit range. Written before the forge folder is deleted. |

## Rules

- Before a task, check `02-forge/00-forge-index.md`. If an active topic covers it, continue that topic.
- A topic moves only after the owner signs off. Record each sign-off in the Sign-off field of the topic index or register entry: the date, a reference (message, link, commit or PR), and any neutral qualifier.
- A closed topic gets a chronicle entry, written before its forge folder is deleted.
- Status lives only in a topic's progress file. Keep it to current state and next actions.
- No runnable code, generated files or engine sidecars in this tree.
- Naming, numbering, indexes, headers and code citation follow the "Documentation conventions" section of [`../docs/README.md`](../docs/README.md). Do not copy them here.

## Transitions

| Owner sign-off | Transition |
| --- | --- |
| Commencement | Create the forge topic with its index, or move it in from `03-horizon/` and delete the horizon item. |
| Acceptance | Weave: facts to `docs/`, lessons to `01-lore/`, any deferred remainder to `03-horizon/`. Write the chronicle entry, then delete the forge topic. |
| Partial acceptance | Weave only the accepted part. The rest stays in forge, or goes to `03-horizon/` if deferred. |
| Deferral | Move the topic to `03-horizon/` with its remaining state summarised. Its lessons so far go to `01-lore/`. |
| Cancellation | Lessons go to `01-lore/`. Write the chronicle entry. Shed the rest. |

Each transition happens in the same session as its sign-off. Passing tests and your own
judgement are not sign-off.
