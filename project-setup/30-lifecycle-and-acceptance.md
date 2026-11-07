# Lifecycle and acceptance

- **Scope:** How does work move between future, active, accepted and cancelled states, and when do the settled-facts docs get updated?
- **Keywords:** lifecycle, acceptance, sign-off, commencement, deferral, cancellation, forge, horizon, chronicle, lore, progress file, docs timing, pending list, awaiting owner check, woven lessons, status wording
- **Status:** current
- **Updated:** 2026-11-07
- **Sources:** distilled from a Godot project's work lifecycle (the project's `agent-docs/README.md` and its `AGENTS.md` *Documentation and work tracking* section)

## Sign-off belongs to the owner

- A topic moves only after the owner signs off its commencement, acceptance, deferral or cancellation. Each sign-off is recorded in the Sign-off field of its record (see [31-sign-off-rules.md](31-sign-off-rules.md)).
- Owner quotes never reach a permanent page as quotes. At acceptance or close-out, convert each quote to a neutral statement, then delete the quotation marks (hub: `practices/owner-words-in-docs.md`).
- Passing tests, a clean review or an agent's own judgement are not sign-off.

## Transitions

- Each sign-off triggers a document transition in the same session. The table of transitions
  (commencement, acceptance, partial acceptance, deferral, cancellation) is in
  [32-transitions.md](32-transitions.md).
- Never start a parallel topic for work that an active topic already covers. Continue that topic.

## When docs change

- A behaviour change ships code-only first. The matching settled-facts doc is updated once, after the owner accepts the item.
- Until then, the pending doc update sits in the topic's progress file.
- There is no separate docs sign-off. The docs are accepted with the implementation they describe.
- Record "implemented + deployed, awaiting owner check" as an entry in the standing list of the progress file, not as a Status value (see [25-header-fields.md](25-header-fields.md) and [26-status-vocabulary.md](26-status-vocabulary.md)). Keep the entry until the owner speaks.

## Lessons are woven, not dumped

- When a topic finishes, fold each lesson into the matching lore subject, deduplicate it, and state the current truth.
- Keep a one-line reversal ("tried X, failed because Y, now Z") only where it prevents a repeat.
- Lore holds no status, plans or open items.

## Progress files

- Status lives only in the progress file: current state and next actions, not a log. Git keeps history.
- Update the progress file in the same session as the work.
