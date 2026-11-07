# Index format

- **Scope:** What must a folder's `00-<folder-slug>-index.md` contain, and how is its table laid out?
- **Keywords:** index, 00 index, folder index, reading guide, children table, one row per child, status column, map, disclosure, root README, tree root, summary, no substance
- **Status:** current
- **Updated:** 2026-11-07
- **Sources:** the owner's lifecycle prompt, section 2.3 (indexes and progressive disclosure); this hub's `project-setup/60-folder-index-template.md` (see [templates/60-folder-index-template.md](templates/60-folder-index-template.md))

Rule first: every folder has one `00-<folder-slug>-index.md`. Tree roots use `README.md`
instead (see below).

## Contents, in order

1. The title and the header block (see [25-headers-and-status.md](25-headers-and-status.md)).
2. A short statement of what the folder covers, in one paragraph.
3. A reading guide: one line per situation, in the form "read X first if you change Y".
4. A table with one row per child.

## The children table

- One row per child file or subfolder, linking to it.
- Columns: the link; a one-line answer to "what question does this child answer?"; and a
  status column only where status applies (forge and horizon folders).
- A status cell holds the state label and a link to the progress file. It never holds status
  content (see [25-headers-and-status.md](25-headers-and-status.md)).

*Why:* the table lets a reader choose a child by its question, without opening each file.

## Content limit

- An index holds no substance beyond the summary, the reading guide and the table.
- Facts belong in the child that answers the question. An index that carries a fact becomes a
  second copy that goes stale.

## Tree roots

- A tree root has `README.md` instead of an index. It states the tree's purpose, links its
  conventions, and maps its top-level entries.
- Conventions are linked, not copied, from the project's `docs/README.md`.

## Maintenance

- Update the index in the same change that adds, renames, moves or removes a child.
- Disclosure runs in one direction: root `README.md`, then the stage or tier index, then the
  topic index, then the file, then the section. Each index points one step down.

*Why:* an index that lags its folder sends a reader to a file that no longer exists, or hides
one that does.
