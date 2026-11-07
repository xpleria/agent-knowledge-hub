# Agent-instruction section: placement and reconciling existing content

- **Scope:** Where does the documentation section go when several agent files exist, and how is existing agent-file content reconciled with it?
- **Keywords:** agent-instruction section, Documentation and work tracking, placement, verbatim copy, defer, import, CLAUDE.md, AGENTS.md, idempotent, heading, reconcile, re-path, replace, Project, Working practices, Definition of done
- **Status:** current
- **Updated:** 2026-11-07
- **Sources:** the owner's lifecycle prompt, section 7.2, merged into this hub 2026-11-07; this hub's `project-setup/templates/10-agents-md-template.md`

Rule first: the agent-instruction file carries one canonical section, headed exactly `## Documentation and work tracking`. Find it by that heading and update it in place. Never add a second copy.

## Placement

- If several agent files exist and one defers to or imports another, put the section in the file being deferred to. Example: a `CLAUDE.md` that imports `AGENTS.md` leaves the section in `AGENTS.md`.
- If the files load independently and cannot import each other, put a verbatim copy in each. List every copy's path in each copy's opening comment, and keep the copies identical.
- If no agent file exists, create `AGENTS.md` containing the section, then add the project's other sections from [templates/10-agents-md-template.md](templates/10-agents-md-template.md).

## Reconciling existing content

- Passages that restate layout, naming or tracking rules are replaced by the section, or cut down to a link to it.
- Every path in the agent files is updated to the new layout.
- Project-specific content is kept with its meaning unchanged: authority hierarchies, hard rules, domain constraints, workflow and deploy instructions.
- Where keeping content requires a change of meaning, the change is listed in the proposal for owner approval (see [62-migration-inventory-and-proposal.md](62-migration-inventory-and-proposal.md)).

## Content and size

- Keep the section under about 30 lines, and leave detail to the READMEs.
- Fill every placeholder. No placeholder may remain in the section's prose, except the project's own fields such as tier names.
- The section lists the two trees and their boundary, the docs tiers in authority order, the stages, the before-a-task steps, the during-and-after rules, the naming summary and the no-code rule. It does not restate the conventions in full (see [18-conventions-location.md](18-conventions-location.md)).

*Why:* an agent reads its root file on every task but never opens the READMEs. The section must carry what every task needs, and nothing that could drift from the conventions page.
