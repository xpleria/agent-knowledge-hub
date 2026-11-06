# Lifecycle and acceptance

- **Scope:** How does work move between future, active, accepted and cancelled states, and when do the settled-facts docs get updated?
- **Keywords:** lifecycle, acceptance, sign-off, commencement, deferral, cancellation, forge, horizon, lore, progress file, docs timing, pending list, awaiting owner check, woven lessons, status wording
- **Status:** current
- **Updated:** 2026-11-01
- **Sources:** distilled from a Godot project's work lifecycle (ganvchi-court `agent-docs/README.md`, `AGENTS.md` *Documentation and work tracking*)

## Sign-off belongs to the owner

- A topic moves only after the project owner signs off. Record the sign-off with the owner's words and a reference in the topic index.
- Passing tests, a clean review or an agent's own judgement are not sign-off.

## Transitions

| Sign-off | Effect |
| --- | --- |
| Commencement | Topic moves from horizon (or nowhere) into the active forge, with playbook, plan and progress files. |
| Acceptance | Facts go to `docs/`, lessons are woven into lore, any deferred remainder goes to horizon, and the forge topic is deleted. |
| Deferral | Topic moves back to horizon. |
| Cancellation | Lessons are woven into lore; the rest is dropped (git keeps it). |

- Never start a parallel topic for work that an active topic already covers. Continue that topic.

## When docs change

- A behaviour change ships code-only first. The matching settled-facts doc is updated once, after the owner accepts the item.
- Until then, the pending doc update sits in the topic's progress file.
- There is no separate docs sign-off. The docs are accepted with the implementation they describe.
- Use the status `implemented + deployed, awaiting owner check` until the owner speaks.

## Lessons are woven, not dumped

- When a topic finishes, fold each lesson into the matching lore subject, deduplicate it, and state the current truth.
- Keep a one-line reversal ("tried X, failed because Y, now Z") only where it prevents a repeat.
- Lore holds no status, plans or open items.

## Progress files

- Status lives only in the progress file: current state and next actions, not a log. Git keeps history.
- Update the progress file in the same session as the work.
