# Proposed decisions: where they live and how their IDs are assigned

- **Scope:** Where does a proposed decision live until it is accepted, and which permanent ID does it take on acceptance?
- **Keywords:** proposed decision, decision record, ADR, permanent ID, reserved ID, ID allocation, next free ID, decisions tier, forge, horizon, Proposed status, migration
- **Status:** current
- **Updated:** 2026-11-07
- **Sources:** the owner's lifecycle prompt, sections 1 and 2.2 (merged into this hub 2026-11-07); [21-numbering-rules.md](21-numbering-rules.md)

Rule first: a proposed decision is not settled, so it never sits in `docs/`, not even under a "Proposed" status.

## While it is proposed

- While it is being decided, it lives in its forge topic, in the decisions file `40-<slug>-decisions.md` (see [33-forge-topic-file-set.md](33-forge-topic-file-set.md)).
- While it is parked, it lives in `03-horizon/` as a horizon item.
- A migration moves every proposed record out of `docs/`, into the forge topic or horizon.

## On acceptance

- Acceptance is the owner's sign-off of the work (see [31-sign-off-rules.md](31-sign-off-rules.md)). The record enters the project's decisions tier and takes the next free permanent ID.
- A proposal may name a reserved ID. If that ID has since been used, the accepted record takes the next free ID instead.
- Where the old ID was cited, note the new ID at each citing place, in the same change.

## Never

- Never write a reserved ID into `docs/` before acceptance. A reservation is not a record.
- Never renumber or reuse a permanent ID. Permanent IDs are exempt from reading-order numbers (see [21-numbering-rules.md](21-numbering-rules.md)).

*Why:* a proposal in `docs/` looks settled to every reader. A reused ID breaks every citation of the older record.
