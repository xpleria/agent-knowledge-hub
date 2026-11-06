# Agent knowledge hub

A central, project-invariant knowledge base for AI agents across projects. Agents
record lessons and scenarios here; new projects bootstrap from it. Agents read
[AGENTS.md](AGENTS.md) first.

## Index

| Path | What it answers |
| --- | --- |
| [AGENTS.md](AGENTS.md) | How should an agent use this hub: recall, contribute, size and git rules? |
| [contribute.md](contribute.md) | How do I add or update a page or recall entry without duplicating one? |
| [recall/00-recall-index.md](recall/00-recall-index.md) | Did we meet this scenario before? Search by keyword. |
| [roles/00-roles-index.md](roles/00-roles-index.md) | What does an orchestrator, implementer, documentation writer or tester do, and what traps apply? |
| [practices/00-practices-index.md](practices/00-practices-index.md) | Which cross-project working habits apply: briefs, evidence, git safety, owner questions? |
| [project-setup/00-project-setup-index.md](project-setup/00-project-setup-index.md) | How is a new project's `docs/` and `agent-docs/` laid out, and how do I bootstrap it? |
| [project-setup/templates/00-templates-index.md](project-setup/templates/00-templates-index.md) | Which starter files (AGENTS.md, agent-docs README, forge topic, horizon item) can I copy? |
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
