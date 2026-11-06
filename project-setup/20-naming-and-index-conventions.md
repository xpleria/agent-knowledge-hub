# Naming and index conventions

- **Scope:** How are files, folders, indexes, headers and splits named and maintained in a new project's docs tree?
- **Keywords:** naming, numbering, NN-slug, index, 00 index, 99 evidence, header, scope, keywords, status, sources, split, promote, merge, gaps, lowercase, no dates, no version suffix
- **Status:** current
- **Sources:** distilled from the conventions in a Godot project's `docs/README.md` and `agent-docs/README.md` (ganvchi-court)

## Names

- Files and folders are lowercase, hyphen-separated, with a two-digit prefix: `NN-topic-slug.md` and `NN-topic-slug/`. The only uppercase file is `README.md`.
- The slug names the topic. Never use a role word alone: `20-pacing-choreography.md`, not `20-choreography.md`, `plan.md` or `PROGRESS.md`.
- No version, status or date suffixes (`-v2`, `-old`, `-final`, `-2026-10-05`). History lives in git.
- Within one tree, a name minus its number is unique, so any file can be cited by its name alone.

## Numbers

- The prefix is the suggested reading order within its directory: dependencies first, importance second, never chronology.
- `00` is reserved for the folder's index. `99` is reserved for an evidence appendix.
- Leave gaps (`10, 20, 30`) so an insertion does not rename siblings. Renumber only when no gap is left, and fix every inbound link in the same change.
- Permanent IDs (for example decision records) are never renumbered.

## Headers

Every Markdown file opens with a title and this block:

- **Scope:** one sentence, the single question the file answers.
- **Keywords:** what a searcher would type: synonyms, identifiers, symbols.
- **Status:** current, or the lifecycle state for work files.
- **Sources:** what the file derives from.

## Indexes

- Every folder has a `00-<folder-slug>-index.md`: what the folder covers, a reading guide ("read X first if you change Y"), and a table with one row per child.
- An index holds no substance beyond that summary. Update it in the same change that adds, renames, moves or removes a child.

## Split and merge triggers

- Split a file that answers two separable questions, or grows past about 300 lines.
- Promote a file to a folder (same number and slug) when a split would yield three or more parts read together.
- Group siblings into a subfolder when a folder exceeds about 12 numbered entries.
- Collapse a folder that holds one content file into a single file.
- Merge two files that are always read together and total under about 150 lines.
