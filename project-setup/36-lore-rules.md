# Lore rules

- **Scope:** What belongs in lore, how is lore organised and woven, and what must lore never hold?
- **Keywords:** lore, lessons, pitfalls, rejected options, rationale, verification methods, newcomer context, woven, merge, deduplicate, replace in place, delete dead, reversal, sources, re-check, no status, subject
- **Status:** current
- **Updated:** 2026-11-07
- **Sources:** the owner's lifecycle prompt, section 4.1 (living memory); owner decisions of 2026-11-07 on lore

Rule first: lore holds everything worth remembering that is not a current fact about the code,
organised by enduring subject. It is never organised by workstream, date or session.

## What lore holds

- Lessons learnt, and pitfalls that cost time.
- Rejected options, and why they lost.
- Rationale that no decision record carries.
- Verification methods that worked.
- Context a newcomer needs to avoid repeating a mistake.

Lore does not hold current code facts (those go to `docs/`), status, plans or open items.

*Why:* a fact about the code goes stale with the code, and a plan goes stale with the work. Lore
keeps what outlives both.

## Organisation

- Organise lore by subject: a subsystem, a domain area or a practice.
- One subject may draw on many finished workstreams.
- Lore topic indexes carry Sign-off as set out in [31-sign-off-rules.md](31-sign-off-rules.md).

## Weaving

- Fold new knowledge into the matching subject, or into a new subject. Merge it with what is
  there and remove duplicates.
- Replace an obsolete statement in place. Delete a dead one: its subject no longer exists, or a
  newer lesson replaces it.
- Never append a correction below a wrong statement. Fix the statement itself.
- Keep a one-line reversal ("tried X; it failed because Y, so Z") only where it stops the same
  mistake recurring. The reversal is the lesson; the old prose is not.

*Why:* a reader needs one current statement. A correction below a wrong one leaves both to be
read, and the reader must decide which is true.

## Sources and checks

- Each lore statement carries `Sources`: the code, docs or decision it rests on.
- When a statement is woven, check it against current code and decisions, as with any other claim.
