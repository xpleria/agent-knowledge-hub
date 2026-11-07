# Split and merge thresholds

- **Scope:** At what size or shape does a project's file, folder or index get split, promoted, grouped, collapsed or merged?
- **Keywords:** thresholds, split, promote, group, collapse, merge, 300 lines, 12 entries, 150 lines, default, override, Documentation conventions, page size, 25 to 60 lines, hub pages
- **Status:** current
- **Updated:** 2026-11-07
- **Sources:** the owner's lifecycle prompt, section 2.7 (default thresholds); the hub's `AGENTS.md` page-size rule, which applies to hub pages only

The thresholds below are defaults for a project's `docs/` and `agent-docs/` trees. A project
may override one only in the "Documentation conventions" section of its `docs/README.md`.

## Default thresholds

| Trigger | Action |
| --- | --- |
| A file answers two or more separable questions. | Split it into sibling files in the same folder. |
| A file passes about 300 lines. | Split it along its questions. If no seam exists, keep it and note why in its index row. |
| A file mixes statement kinds (see [27-one-question-and-citations.md](27-one-question-and-citations.md)). | Split it by kind. |
| A split would yield three or more parts read together. | Promote the file to a folder with the same number and slug (see [21-numbering-rules.md](21-numbering-rules.md)). |
| A folder passes about 12 numbered entries, not counting `00` and `99`. | Group related siblings into a subfolder. |
| A folder has one content file besides its index. | Collapse it into a single file that keeps the folder's number and slug. |
| Two files are always read together and total under about 150 lines. | Merge them. |
| A file or folder is empty after shedding. | Delete it and update its index. |

A folder must earn its existence: it needs at least two content children. Depth is
unlimited.

*Why:* a file that answers one question is retrieved and read whole. A folder with one child
adds a hop to every lookup without adding a split.

## Overrides

- Write an override in `docs/README.md` under "Documentation conventions": the threshold, its
  new value, and the reason.
- An override applies to the project that writes it. The hub's defaults stay unchanged for
  every other project.
- Any other project-layout convention is also overridable only there. On all other matters
  the project's `AGENTS.md` wins over hub pages.

*Why:* one written place lets an agent find every local change before it splits or merges a
file.

## Hub pages are a separate rule

- Hub pages hold 25 to 60 lines each, with one fact per file (hub `AGENTS.md`).
- The 25 to 60 line limit applies to hub pages only. A project's files use the thresholds
  above, not this limit.

*Why:* hub pages are read in one pass by many projects, so they stay short. Project files
grow with their subject and are read as needed.
