# Numbering rules

- **Scope:** What do the number prefixes in a project directory mean, and which entries are exempt from reading-order numbers?
- **Keywords:** numbering, NN prefix, reading order, gaps, 00 index, 99 evidence, permanent ID, ADR, decision record, promote, promoted folder, encoded parent number, exempt, evidence files, requirement ID
- **Status:** current
- **Updated:** 2026-11-07
- **Sources:** the owner's lifecycle prompt, section 2.2 (numbers mean reading order) and section 2.6 (evidence exemption)

Rule first: every entry in a project directory, files and subfolders alike, takes a two-digit
prefix from one shared sequence for that directory.

## Reading order

- The number is the suggested reading order: dependencies first, importance second. It is
  never chronology.
- The number is local to its directory. Do not encode the parent's number into a child
  (for example `0302-...`).
- `00` is reserved for the folder's index (see [23-index-format.md](23-index-format.md)).
  `99` is reserved for an evidence appendix.

*Why:* a reader working top-down must never meet a concept before it is defined. An encoded
parent number forces renames down the whole subtree when a parent moves.

## Gaps and renumbering

- Leave gaps when allocating (10, 20, 30, or steps of 5 in a busy directory), so an
  insertion does not renumber its siblings.
- Renumber only when no gap is left, and update every inbound reference in the same change.

## Promotion

- A file promoted to a folder keeps its number and slug: `20-billing.md` becomes
  `20-billing/`.
- The new folder's contents are numbered from scratch, starting with `00-billing-index.md`.

## Permanent IDs and exempt entries

- Decision records, and any document whose number is cited as an identifier (for example
  `ADR-0007`), keep sequential IDs that are never reused. They are exempt from reading-order
  numbering and are never renumbered.
- An accepted proposal takes the next free permanent ID. If the proposal reserved an ID that
  has since been used, it takes a new one, and the change is noted where the old ID was
  cited.
- Requirement IDs and rule section numbers that appear inside text are never changed by a
  migration.
- Evidence files inside a `99-<topic-slug>-evidence/` folder are exempt from numbering. They
  are cited, not read in sequence.

*Why:* a cited ID that changes silently breaks every reference to it. Evidence is looked up
by what it shows, so a sequence number adds nothing.
