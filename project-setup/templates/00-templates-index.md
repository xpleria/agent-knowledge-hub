# Templates index

- **Scope:** Which starter files can an agent copy into a new project, and what does each one hold?
- **Keywords:** templates, starter, AGENTS.md, agent-docs README, forge topic, horizon item, chronicle entry, copy, placeholders, bootstrap
- **Status:** current
- **Updated:** 2026-11-07
- **Sources:** this hub's `project-setup/40-bootstrap-checklist.md`

## Reading guide

- Copying a starter file for a new project: read the row for that file below, then its template.
- Writing a folder index: read [60-folder-index-template.md](60-folder-index-template.md).

Copy a template into the new project, then replace every `<placeholder>`. Delete any
section that does not apply. Do not leave a placeholder in a committed file.

| Template | Copy it to | Use when |
| --- | --- | --- |
| [10-agents-md-template.md](10-agents-md-template.md) | project root `AGENTS.md` | Starting any project |
| [20-agent-docs-readme-template.md](20-agent-docs-readme-template.md) | `agent-docs/README.md` | Creating the work-lifecycle tree |
| [30-forge-topic-template.md](30-forge-topic-template.md) | `agent-docs/02-forge/<NN-topic-slug>/` progress file | The owner commits to a workstream |
| [40-horizon-item-template.md](40-horizon-item-template.md) | `agent-docs/03-horizon/<NN-topic-slug>/` item file | Future work is recorded but not planned |
| [50-chronicle-entry-template.md](50-chronicle-entry-template.md) | `agent-docs/04-chronicle/<NN-topic-slug>.md` | A forge topic is closed, before its forge folder is deleted |
| [60-folder-index-template.md](60-folder-index-template.md) | `00-<folder-slug>-index.md` in any folder | A folder gets its first child, or a child is added or removed |
