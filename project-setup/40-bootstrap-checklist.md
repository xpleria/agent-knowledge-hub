# Bootstrap checklist for a new project

- **Scope:** What does an agent create, in what order, when it sets up a new project to use the hub's conventions?
- **Keywords:** bootstrap, new project, setup, checklist, AGENTS.md, docs, agent-docs, forge, horizon, lore, chronicle, templates, gitignore, secrets, first commit
- **Status:** current
- **Updated:** 2026-11-07
- **Sources:** this hub's `project-setup/` pages and `templates/`; derived from a Godot project's layout

Work through the steps in order. An existing project with docs, notes or agent files follows [60-migrate-existing-project.md](60-migrate-existing-project.md) instead. Commit a group only when commits are permitted (see [45-git-rules.md](45-git-rules.md)).

1. **Ask the owner** for the project's purpose, its engine or stack, its target platforms and its deploy target. Record the answers as neutral statements in the project's AGENTS.md and docs; quote the owner only in a transient note. Do not guess a rule.
2. **Create the repository** locally. Do not add a remote or push unless the owner asks.
3. **Create `docs/README.md`** with a "Documentation conventions" section (see [18-conventions-location.md](18-conventions-location.md)), the authority order of the tiers, and a map. Create a tier folder only when it has content, each with its `00-*-index.md`. List planned tiers in the README, not as empty folders.
4. **Create `agent-docs/`** from [templates/20-agent-docs-readme-template.md](templates/20-agent-docs-readme-template.md), with `01-lore/`, `02-forge/`, `03-horizon/` and `04-chronicle/`, each with its `00-<stage>-index.md` (copy [templates/60-folder-index-template.md](templates/60-folder-index-template.md)). The chronicle starts empty.
5. **Write the agent-instruction section** in the project's `AGENTS.md`. Create `AGENTS.md` from [templates/10-agents-md-template.md](templates/10-agents-md-template.md) if it is absent. Keep it short. Placement rules are in [65-agent-instruction-section.md](65-agent-instruction-section.md).
6. **Add the first forge topic** only when the owner commits to work. Start from [templates/35-forge-index-template.md](templates/35-forge-index-template.md), whose Sign-off records the commencement. Add the progress file from [templates/30-forge-progress-template.md](templates/30-forge-progress-template.md) once work has happened. Add horizon items from [templates/40-horizon-item-template.md](templates/40-horizon-item-template.md) for anything later.
7. **Set up ignores and secrets.** Ignore build output, editor caches, generated sidecars and secret files. Credentials go in a gitignored env file that the deploy script reads as data (see [50-deploy-and-verify-habits.md](50-deploy-and-verify-habits.md)).
8. **Set up tests and the verification habit** (see [50-deploy-and-verify-habits.md](50-deploy-and-verify-habits.md)), so the first feature ships with a test.
9. **Point agents at the hub.** Give them the hub's `AGENTS.md` and the role pages they hold.
10. **Commit each group**, when commits are permitted. Never push unless the owner asks.

Checks before you finish:

- Every page has the header block (see [25-header-fields.md](25-header-fields.md)), and every folder has its index (see [23-index-format.md](23-index-format.md)).
- No link in `docs/` points into `agent-docs/`.
- No secret is in any tracked file, and no credential file is staged.
- `git status` is clean after the last commit, or shows only the intended paths when nothing was committed.
