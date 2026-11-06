# agent-docs

- **Scope:** What does the work-lifecycle tree hold, and how does an agent move through it?
- **Keywords:** agent-docs, lore, forge, horizon, lifecycle, work tracking, progress, index, sign-off
- **Status:** current
- **Updated:** <YYYY-MM-DD>
- **Sources:** the project's `docs/README.md`; the hub's `project-setup/30-lifecycle-and-acceptance.md`

This tree holds the work lifecycle of this project: what is in progress, what may come
later, and the lessons learned along the way. Settled facts live in
[`../docs/README.md`](../docs/README.md). `agent-docs/` may link into `docs/`; `docs/`
never links back.

## Stages

| Stage | Folder | What it holds |
| --- | --- | --- |
| 01 | [`lore/`](lore/00-lore-index.md) | Lessons, rationale and pitfalls from finished or cancelled work, by subject. A living record. |
| 02 | [`forge/`](forge/00-forge-index.md) | Active work, one topic folder per workstream. |
| 03 | [`horizon/`](horizon/00-horizon-index.md) | Future work the owner has not committed to plan yet. |

## Rules

- Before a task, check the forge index. If an active topic covers it, continue that topic.
- A topic moves only after the owner signs off. Record the sign-off in the topic index with the owner's words.
- Status lives only in a topic's progress file. Keep it to current state and next actions.
- Files are `NN-topic-slug.md` and folders `NN-topic-slug/`, each with a `00-*-index.md`.
- No runnable code, generated files or engine sidecars in this tree.
- Code comments cite `docs/` facts or decision IDs, never paths in this tree.
