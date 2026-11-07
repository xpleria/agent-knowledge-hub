# Templates index

- **Scope:** Which starter files can an agent copy into a new project, and what does each one hold?
- **Keywords:** templates, starter, AGENTS.md, agent-docs README, forge index, forge progress, horizon item, chronicle entry, copy, placeholders, bootstrap
- **Status:** current
- **Updated:** 2026-11-07
- **Sources:** this hub's `project-setup/40-bootstrap-checklist.md`

## Reading guide

- Copying a starter file for a new project: read the row for that file below, then its template.
- Starting a forge topic: copy the forge index template first; add the progress template once work has happened.
- Writing a folder index: read [60-folder-index-template.md](60-folder-index-template.md).

Copy a template into the new project, then replace every `<placeholder>`. Delete any
section that does not apply. Do not leave a placeholder in a committed file.

| Template | Copy it to | Question it answers |
| --- | --- | --- |
| [10-agents-md-template.md](10-agents-md-template.md) | project root `AGENTS.md` | Where do agents find the project's rules and its tracking habits? |
| [20-agent-docs-readme-template.md](20-agent-docs-readme-template.md) | `agent-docs/README.md` | How does an agent move through the work-lifecycle tree? |
| [35-forge-index-template.md](35-forge-index-template.md) | `agent-docs/02-forge/<NN-topic-slug>/00-<slug>-index.md` | What is this workstream's goal, and which file answers which question? |
| [30-forge-progress-template.md](30-forge-progress-template.md) | `agent-docs/02-forge/<NN-topic-slug>/30-<slug>-progress.md` | What is verified, what is broken, and what is next in this workstream? |
| [40-horizon-item-template.md](40-horizon-item-template.md) | `agent-docs/03-horizon/NN-<topic-slug>.md` | What future work is recorded, where did it come from, and what must be settled before it starts? |
| [50-chronicle-entry-template.md](50-chronicle-entry-template.md) | `agent-docs/04-chronicle/NN-<topic-slug>.md` | When and how did this forge topic close, and where did its facts and lessons go? |
| [60-folder-index-template.md](60-folder-index-template.md) | `00-<folder-slug>-index.md` in any folder | Which children does this folder hold, and which question does each one answer? |

Template files that carry a `<placeholder>` in their header are copied, then filled in.
A committed file never keeps a placeholder.
