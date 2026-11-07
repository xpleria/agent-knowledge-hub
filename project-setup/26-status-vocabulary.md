# Status vocabulary

- **Scope:** Which Status values may a page carry, and what does a Status value not mean?
- **Keywords:** status, status values, stage label, current, lore, forge active, forge paused, forge blocked, horizon deferred, horizon idea, chronicle, paused versus deferred, awaiting owner check, standing list, progress file
- **Status:** current
- **Updated:** 2026-11-07
- **Sources:** the owner's lifecycle prompt, section 2.4 (the Status field) and section 4.2 (paused work); the hub's `project-setup/30-lifecycle-and-acceptance.md` for the progress file

Rule first: a page's Status is one value from the table below. It names the stage the page is in,
not the status of the work inside it.

| Stage | Values |
| --- | --- |
| Docs | `current` |
| Lore | `lore` |
| Forge | `forge: active`, `forge: paused`, `forge: blocked` |
| Horizon | `horizon: deferred`, `horizon: idea` |
| Chronicle | `chronicle` |

## What a value does not mean

- Paused is not deferred. Paused work stays in forge, with `forge: paused` and a reason in its
  progress file. Deferred work moves to horizon.
- `implemented + deployed, awaiting owner check` is not a Status value. It is an entry in the
  standing list of the progress file.

*Why:* a paused topic that is moved to horizon looks deferred to a reader and loses its place
in the forge index. An entry in a list cannot be mistaken for a stage.

## Stage label and status content

- The header Status is the stage label. Only the progress file holds status content: current
  state, next actions and blockers.
- An index carries a one-line summary of a topic's status and a link to its progress file. It
  never repeats the status content.

*Why:* two copies of status content drift apart, and then a reader trusts the wrong one.
