# Agent knowledge hub

- **Scope:** What is this hub, where does an agent start, and what does each folder hold?
- **Keywords:** hub, entry file, start here, index, map, recall, roles, practices, project-setup, engines, boundary
- **Status:** current
- **Updated:** 2026-11-07
- **Sources:** this hub's `AGENTS.md`, `contribute.md` and the index pages it links

A central, project-invariant knowledge base for AI agents across projects. Agents
record lessons and scenarios here; new projects bootstrap from it. This `README.md` is
the hub's entry file. Read it first, then the rules in [AGENTS.md](AGENTS.md).

## Start here

- **Setting up a new project:** [project-setup/00-project-setup-index.md](project-setup/00-project-setup-index.md), then the bootstrap checklist and [templates](project-setup/templates/00-templates-index.md).
- **Migrating an existing project into `docs/` and `agent-docs/`:** [project-setup/60-migrate-existing-project.md](project-setup/60-migrate-existing-project.md).
- **Delegating or orchestrating:** [roles/orchestrator.md](roles/orchestrator.md), then [practices/delegation-briefs.md](practices/delegation-briefs.md).
- **Implementing, testing or documenting in a role:** the page for each role you hold in [roles/00-roles-index.md](roles/00-roles-index.md), and [practices/00-practices-index.md](practices/00-practices-index.md) before committing.
- **Recalling a past scenario:** grep `recall/` by keyword, starting at [recall/00-recall-index.md](recall/00-recall-index.md).
- **Contributing:** [contribute.md](contribute.md), under the rules in [AGENTS.md](AGENTS.md).

## Index

| Path | What it answers |
| --- | --- |
| [AGENTS.md](AGENTS.md) | How should an agent use this hub: recall, contribute, size and git rules? |
| [contribute.md](contribute.md) | How do I add or update a page or recall entry without duplicating one? |
| [recall/00-recall-index.md](recall/00-recall-index.md) | Did we meet this scenario before? Search by keyword. |
| [roles/00-roles-index.md](roles/00-roles-index.md) | What does an orchestrator, implementer, documentation writer or tester do, and what traps apply? |
| [practices/00-practices-index.md](practices/00-practices-index.md) | Which cross-project working habits apply: briefs, evidence, git safety, owner questions? |
| [project-setup/00-project-setup-index.md](project-setup/00-project-setup-index.md) | How is a new project's `docs/` and `agent-docs/` laid out, and how do I bootstrap it? |
| [project-setup/60-migrate-existing-project.md](project-setup/60-migrate-existing-project.md) | How do I migrate a project that already has docs, notes or agent files? |
| [project-setup/templates/00-templates-index.md](project-setup/templates/00-templates-index.md) | Which starter files (AGENTS.md, agent-docs README, forge topic, horizon item, chronicle entry) can I copy? |
| [engines/00-engines-index.md](engines/00-engines-index.md) | Which engine-specific traps are broadly useful? (Labelled per engine.) |

## Tree

```text
agent-knowledge-hub/
  AGENTS.md  README.md  contribute.md
  recall/          scenario journal, searchable by keyword
  roles/           orchestrator, implementer, documentation writer, tester
  practices/       cross-project working practices
  project-setup/   bootstrap guide and templates/
  engines/         engine-specific pages, clearly labelled
```

## Boundary

Only facts that hold across projects belong here. Rules, item IDs, product names and
credentials stay in the project that owns them.
