# Code versus docs: which side is wrong when they disagree

- **Scope:** When the code and a docs page disagree, which side is wrong, and what is done about it?
- **Keywords:** code versus docs, normative, descriptive, conflict, defect, owner ruling, ambiguous rule, migration conflict, fix neither side, code is wrong, stop and ask
- **Status:** current
- **Updated:** 2026-11-07
- **Sources:** the owner's lifecycle prompt, sections 1 and 3 (merged into this hub 2026-11-07); this hub's `project-setup/templates/10-agents-md-template.md`

Rule first: the kind of fact decides which side is wrong.

## Normative fact: a rule, requirement or accepted decision

- The code is wrong. Fix the code, or ask the owner whether the rule itself has changed.
- Never infer a normative fact from code when a `docs/` page states it.
- If the rule is ambiguous, stop and ask the owner.
- Only an owner decision changes a normative page (see [12-docs-tiers-and-glossary.md](12-docs-tiers-and-glossary.md)).

## Descriptive fact: what the code, tests and tooling do now

- The docs page is wrong. A descriptive page that no longer matches the code is a defect, fixed in the same change as the code (see [30-lifecycle-and-acceptance.md](30-lifecycle-and-acceptance.md), "When docs change").

## During a migration

- Fix neither side. Record the conflict as "conflict: <docs path> says X; <code path and symbol> does Y".
- Put the record in the active forge topic doing related work, or in `03-horizon/` when no topic does.
- List each conflict among the owner decisions in the migration proposal.

## Citing code

- Permanent pages (docs, lore, the hub) cite code as the path and the symbol or heading. No line numbers there; a line number goes stale with the next edit.
- Transient pages (forge, horizon, evidence) may cite `path:line`. Prefer the symbol where one exists, and re-check each anchor when the cited file changes (see [27-one-question-and-citations.md](27-one-question-and-citations.md)).

*Why:* a rule in code is a guess about intent, and a rule in docs is the record of intent. Only the owner settles which one was meant.
