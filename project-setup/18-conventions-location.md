# Where a project's documentation conventions live

- **Scope:** Where is each part of the documentation convention written, so that every rule is stated once?
- **Keywords:** Documentation conventions, docs/README.md, agent-docs/README.md, AGENTS.md, summary, link, copy, single source, naming, numbering, thresholds, overrides
- **Status:** current
- **Updated:** 2026-11-07
- **Sources:** the owner's lifecycle prompt, section 7.1 (merged into this hub 2026-11-07); this hub's `project-setup/templates/20-agent-docs-readme-template.md`

Rule first: the shared conventions are written once, in the project's `docs/README.md`, under a heading "Documentation conventions". Every other file links to that section and does not copy it.

## Three files, three jobs

| File | Carries |
| --- | --- |
| `docs/README.md`, section "Documentation conventions" | Shared conventions: tree boundary, names, numbers, indexes, headers, evidence, thresholds and their overrides. |
| `agent-docs/README.md` | Lifecycle rules: stages, transitions, sign-off, where status lives. Links to the conventions section. |
| `AGENTS.md` | The always-loaded summary: the section headed "Documentation and work tracking", from `templates/10-agents-md-template.md`. |

*Why:* an agent loads `AGENTS.md` on every task but may not open the READMEs. A rule copied into two files drifts apart, so each rule has one home and the other files point to it.

## Rules

- Do not copy a naming, numbering or threshold rule into a second file. Link to the section.
- Write each threshold override in the "Documentation conventions" section, with its new value and its reason (see [22-split-and-merge-thresholds.md](22-split-and-merge-thresholds.md)).
- State the `docs/` tiers in authority order in the same README, with a map of its entries. List planned tiers rather than creating empty folders (see [12-docs-tiers-and-glossary.md](12-docs-tiers-and-glossary.md)).
- The agent-docs README template links to the conventions and copies no naming rule.

## Precedence

- An override written in this section applies. A layout rule written anywhere else does not (see [16-precedence-rule.md](16-precedence-rule.md)).
