# Horizon item shape

- **Scope:** What is the minimum shape of a horizon item, when does it grow into a folder, and how does it leave horizon?
- **Keywords:** horizon, item, single file, NN-slug.md, origin, raised by, constraints, prerequisites, what is needed to start, open questions, owner's words, commencement, promotion, folder, delete, pointer stub, numbering, intended sequence, dependency
- **Status:** current
- **Updated:** 2026-11-07
- **Sources:** the owner's lifecycle prompt, section 4.3 (future work); owner decisions of 2026-11-07 on horizon shape

Rule first: one horizon item is one file, `03-horizon/NN-<slug>.md`, copied from
`templates/40-horizon-item-template.md`. It becomes a folder only when its content needs one.

## Minimum content

- What the work is and why it matters.
- Origin: who raised it and when, and a link to the lore page or forge topic it was deferred from.
- Known constraints and prerequisites.
- What would be needed to start.
- Commencement criteria: the owner commits and signs off, and the open questions are answered.

*Why:* an item without an origin cannot be traced, and one without a start condition is a wish.

## Growing

- When one item needs more than one file, promote it to `03-horizon/NN-<slug>/` with
  `00-<slug>-index.md`, using the rules in [22-split-and-merge-thresholds.md](22-split-and-merge-thresholds.md).
  The number and slug stay the same.
- Add files only when they have content: a brief, carried-over findings or evidence.

## Numbering

- Number items by intended sequence where it is known, otherwise by dependency. Numbers
  follow [21-numbering-rules.md](21-numbering-rules.md).
- Each stage index lists its items with a status cell (`horizon: deferred | idea`).

## Sign-off

- Sign-off is `none` until a deferral creates the item. The deferral then records its date and
  reference (see [31-sign-off-rules.md](31-sign-off-rules.md)).

## Leaving horizon

- On commencement, delete the horizon item (or folder) and fix every inbound link in the same change.
- Leave no pointer stub. The forge index records the origin instead.

*Why:* a stub in the old place is a second copy of the item, and it looks deferred after the
work has started.
