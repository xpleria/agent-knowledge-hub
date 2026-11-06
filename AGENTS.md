# Agent knowledge hub: rules for agents

- **Scope:** How does an agent use this hub to recall, set up a project, and contribute?
- **Keywords:** hub, recall, contribute, project-invariant, size, header, git, bootstrap
- **Status:** current

## What this is

A central, project-invariant knowledge base for agents across projects. It holds
lessons, role guidance, working practices and project-setup templates. It holds no
project rules, item IDs, product names or credentials.

## Use it

- **Recall:** when the owner asks "what happened when...", grep `recall/` by keyword:
  `grep -ril "<keyword>" recall/` then read the entry. Start at `recall/00-recall-index.md`.
- **Set up a project:** read `project-setup/00-project-setup-index.md`, follow the
  bootstrap checklist, copy from `project-setup/templates/`. Why: every project then
  shares one docs layout and acceptance flow.
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

- Header: Scope (one question), Keywords, Status, Sources or Source project.
- 25 to 60 lines per page, one fact per file, rule first then the reason. Why: pages
  are read into context, so size is a cost.
- No dates, no incident narration, no item IDs. Describe the pattern, not the event.
- Every folder has a `00-*-index.md`; add a row in the same change as the page.

## Git rules

- Local commits per logical change, message names the folder (`roles: ...`).
- No remote and no push unless the owner says so. Never force-push.
- Never discard work with checkout, restore or reset; use `git stash push -u -m <name>`.
- Never write secrets, tokens or `.env` contents here.
