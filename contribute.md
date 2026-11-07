# How to contribute to the hub

- **Scope:** What does an agent do when it learns something worth keeping, and how does it avoid duplicating existing pages?
- **Keywords:** contribute, add page, update page, index, recall entry, duplicate, invariant, project-specific, size, header
- **Status:** current
- **Updated:** 2026-11-07
- **Sources:** this hub's `AGENTS.md`; the page-size and header rules in `AGENTS.md`

## Decide whether the fact belongs here

1. Ask: would this still be true in a different project? If yes, it is a candidate.
2. If it names a specific repo's rule, item ID, product, host, path or credential, it stays
   in that project. Do not add it here, even as an example.
3. If you are not sure, put it in your report to the owner instead of the hub.

## The hub's own folders are not a project

- Project rules do not govern the hub. Numbering, the 300-line split and the docs tiers in
  `project-setup/` apply to a project's docs, never to the hub's folders.
- The 25-to-60-line limit and the header block apply to hub pages only.
- `README.md` at the hub root is the entry file. Each subfolder is indexed by its `00-*-index.md`.


## Find an existing home first

1. Search: `grep -ril "<keyword>" recall/ roles/ practices/ project-setup/ technologies/`
2. If a page already covers the subject, update that page. Add a rule only once.
3. If an entry already describes the scenario, add a line to it rather than a new file.

## Add or update a page

1. Write the header: Scope (one question), Keywords (what a searcher types), Status, Updated, Sources.
2. Keep it to 25 to 60 lines (hub pages only). One fact per file. Rule first, then the reason.
3. Add a row to the nearest index in the same change.
4. Commit with a message that names the folder, for example `practices: add evidence rule`.

## Add a recall entry

1. Copy the shape of an existing entry in `recall/`. Use the next free number in steps of 10.
2. Header fields: Scope, Keywords, Status, Updated, **Source project** (the project it came from).
3. Body: what happened in general terms, then the rule, then when it applies. Keep it short.
4. Add one row to `recall/00-recall-index.md`.

## Avoid duplicates

- Grep the keywords before writing. Two entries describing the same trap are a defect.
- If a new scenario extends an old one, merge the new detail into the old entry.
- Replace obsolete guidance; do not append a contradicting note under it.
- The one exception is a dated record, such as a project's chronicle entry (see
  `project-setup/templates/50-chronicle-entry-template.md`). It is corrected only by a dated
  note at its end, never by rewriting the text above.
