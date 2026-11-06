# Bootstrap checklist for a new project

- **Scope:** What does an agent create, in what order, when it sets up a new project to use the hub's conventions?
- **Keywords:** bootstrap, new project, setup, checklist, AGENTS.md, docs, agent-docs, forge, horizon, lore, templates, gitignore, secrets, first commit
- **Status:** current
- **Sources:** this hub's `project-setup/` pages and `templates/`; derived from a Godot project's layout (ganvchi-court)

Work through the steps in order. Commit after each group.

1. **Ask the owner** for the project's purpose, its engine or stack, its target platforms and its deploy target. Record the answers as the owner's words. Do not guess a rule.
2. **Create the repository** locally. Do not add a remote or push unless the owner asks.
3. **Write the project's `AGENTS.md`** from `templates/10-agents-md-template.md`. Keep it short: it links to the docs, states the hard rules, and carries the hub paragraph.
4. **Create `docs/`** with a `README.md` that states the authority order. Add the tier folders you need, each with a `00-*-index.md`. Do not create empty tiers.
5. **Create `agent-docs/`** from `templates/20-agent-docs-readme-template.md`, with `lore/`, `forge/` and `horizon/` and their index files.
6. **Add the first forge topic** only when the owner commits to work. Start from `templates/30-forge-topic-template.md`. Add horizon items from `templates/40-horizon-item-template.md` for anything later.
7. **Set up ignores.** Ignore build output, editor caches, and secret files. Credentials go in a gitignored env file that tools read as data.
8. **Set up tests and the verification habit** (see [50-deploy-and-verify-habits.md](50-deploy-and-verify-habits.md)), so the first feature ships with a test.
9. **Read the hub.** Point the new project's agents at the hub's `AGENTS.md` and the role pages they hold.
10. **Commit** the scaffold with a message such as `docs: bootstrap project docs structure`.

Checks before you finish:

- Every page has the header block and every folder has its index.
- No link in `docs/` points into `agent-docs/`.
- No secrets are in any tracked file.
- `git status` is clean after the last commit.
