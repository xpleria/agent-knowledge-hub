# agent-docs

- **Scope:** What does the work-lifecycle tree hold, and how does an agent move through it?
- **Keywords:** agent-docs, lore, forge, horizon, chronicle, lifecycle, work tracking, progress, index, sign-off
- **Status:** current
- **Updated:** 2026-11-07
- **Sources:** the project's `docs/README.md`; the hub's `project-setup/30-lifecycle-and-acceptance.md`

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
- A topic moves only after the owner signs off. Record the sign-off in the topic index as "accepted by the owner on <date>", with any plain-language qualifier the owner gave.
- A closed topic gets a chronicle entry, written before its forge folder is deleted.
- Status lives only in a topic's progress file. Keep it to current state and next actions.
- Files are `NN-topic-slug.md` and folders `NN-topic-slug/`, each with a `00-*-index.md`.
- No runnable code, generated files or engine sidecars in this tree.
- Code comments cite `docs/` facts or decision IDs, never paths in this tree.
