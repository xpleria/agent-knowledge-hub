# Agent knowledge hub: rules for agents

- **Scope:** How does an agent use this hub to recall, set up or migrate a project, and contribute?
- **Keywords:** hub, recall, contribute, project-invariant, size, header, git, bootstrap, migration
- **Status:** current
- **Updated:** 2026-11-07

## Start here

- **Setting up a new project:** [project-setup/00-project-setup-index.md](project-setup/00-project-setup-index.md), then the bootstrap checklist and [templates](project-setup/templates/00-templates-index.md).
- **Migrating an existing project's docs:** [project-setup/60-migrate-existing-project.md](project-setup/60-migrate-existing-project.md). On layout the hub governs ([precedence](project-setup/16-precedence-rule.md)).
- **Delegating or orchestrating:** [roles/orchestrator.md](roles/orchestrator.md), then [practices/delegation-briefs.md](practices/delegation-briefs.md).
- **Implementing, testing or documenting in a role:** the page for each role you hold in [roles/00-roles-index.md](roles/00-roles-index.md), and [practices/00-practices-index.md](practices/00-practices-index.md) before committing.
- **Recalling a past scenario:** grep `recall/` by keyword, starting at [recall/00-recall-index.md](recall/00-recall-index.md).
- **Contributing:** [contribute.md](contribute.md), under the rules in this file.

## What this is

A central, project-invariant knowledge base for agents across projects. It holds
lessons, role guidance, working practices and project-setup templates. It holds no
project rules, item IDs, product names or credentials. Exception: a recall entry's
`Source project` field. Sources lines say "a Godot project", not its name.

## Use it

- **Recall:** when the owner asks "what happened when...", grep `recall/` by keyword:
  `grep -ril "<keyword>" recall/` then read the entry.
- **Set up a project:** follow the bootstrap checklist, copy from `project-setup/templates/`.
  Why: every project then shares one docs layout and acceptance flow.
- **Work in a role:** read the page in `roles/` for each role you hold (one agent may
  hold several) and `practices/` before delegating or committing.

## Contribute

- Add or update a page when you learn something that holds across projects. Follow
  `contribute.md`: search first, update before adding, index every new page.
- Keep project-specific facts in the project. Why: the hub must read the same in
  every project and stay small.
- If unsure whether a fact is project-invariant, put it in your report to the owner,
  not in the hub.

## Page rules

- Header: Scope (one question), Keywords, Status, Updated, Sources or Source project.
- 25 to 60 lines per page is the recommended size, not a hard limit; one fact per file,
  rule first then the reason. It applies to hub pages only, not to project docs. A
  project's `AGENTS.md` may be longer when the project needs it. Why: pages are read
  into context, so size is a cost.
- Dates only in the `Updated` header field (YYYY-MM-DD), the date of the last substantive
  change. No incident narration, no item IDs. Describe the pattern, not the event.
  Exception: a project's dated records (chronicle entries, sign-offs, decision dates)
  keep their dates. They state owner decisions in neutral words and never quote the
  owner, because the date is part of the record.
- Owner words: transient docs (forge, horizon, delegation briefs, working notes) may quote
  the owner verbatim; permanent pages never do. See
  [practices/owner-words-in-docs.md](practices/owner-words-in-docs.md).
- Every folder has a `00-*-index.md`; add a row in the same change as the page. The hub
  root is entered through `README.md`.

## Git rules

- Commit each logical change locally when the owner or project permits commits; message names the folder (`roles: ...`).
- No remote and no push unless the owner says so. Never force-push.
- Never discard work with checkout, restore or reset; use `git stash push -u -m <name>`.
- Never write secrets, tokens or `.env` contents here.
