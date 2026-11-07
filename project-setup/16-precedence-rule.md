# Precedence between the hub, a project's agent file and its conventions

- **Scope:** Which rule wins when the hub, a project's agent file and its documentation conventions disagree?
- **Keywords:** precedence, override, hub governs, documentation layout, AGENTS.md wins, Documentation conventions, threshold override, conflict, owner, ask
- **Status:** current
- **Updated:** 2026-11-07
- **Sources:** the owner's lifecycle prompt, section 0 (merged into this hub 2026-11-07); this hub's `practices/00-practices-index.md` and `roles/00-roles-index.md`

Rule first: on documentation layout the hub governs. On every other matter the project's `AGENTS.md` wins over hub role and practice pages.

## Documentation layout

- Layout means the folders, numbering, names, indexes, headers, thresholds and evidence rules set out in `project-setup/`.
- A project may override a threshold or convention only in the "Documentation conventions" section of its `docs/README.md` (see [18-conventions-location.md](18-conventions-location.md)).
- An override written anywhere else does not count. The hub default applies.

## Everything else

- The project's `AGENTS.md` wins over the hub pages in `roles/` and `practices/`.
- Those hub pages say the same: a project's own rules override them.

## When a conflict matters

- If a project's own file conflicts with a layout rule, follow the hub default and say so in the report to the owner.
- If you are unsure whether a conflict is about layout, ask the owner. Do not decide it alone.
- A migration lists each such conflict as an owner decision in its proposal.

*Why:* layout is shared by every project, so one rule settles it. The project's own rules govern its work, and only the owner decides between them.
