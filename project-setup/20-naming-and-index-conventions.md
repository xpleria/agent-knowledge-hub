# Naming conventions

- **Scope:** How are the names of files, folders and evidence files built in a project's docs and agent-docs trees?
- **Keywords:** naming, slug, lowercase, hyphen, role words, index, plan, progress, playbook, findings, decisions, log, evidence, notes, suffix, version, date, unique name, unambiguous
- **Status:** current
- **Updated:** 2026-11-07
- **Sources:** the owner's lifecycle prompt, section 2.1 (names); the hub's earlier naming conventions, now split across the pages linked below

Rule first: names are lowercase and hyphen-separated, and the slug names the topic. Within a
tree, a name with its number removed is unique.

## Shape

- Files are `NN-topic-slug.md`. Folders are `NN-topic-slug/`. The number is governed by
  [21-numbering-rules.md](21-numbering-rules.md).
- The index of a folder is `00-<folder-slug>-index.md`. The role word `index` is allowed there
  because the folder slug says which index it is.
- Evidence files inside a `99-<topic-slug>-evidence/` folder are lowercase, hyphen-separated and
  descriptive. They carry no number.
- Uppercase names are kept only for conventional files (see
  [15-uppercase-and-root-files.md](15-uppercase-and-root-files.md)).

## The slug names the topic

- Never use a role word alone as a slug. Role words are `index`, `plan`, `progress`,
  `playbook`, `findings`, `decisions`, `log`, `evidence` and `notes`.
- Write `20-pacing-plan.md`, not `20-plan.md`. Write `10-checkout-retry-playbook.md`, not
  `PLAYBOOK.md`.
- A file must be unambiguous when read outside its folder.

*Why:* a search hit or a citation shows only the path. A bare role word says nothing about
which topic it belongs to.

## Names are unique within a tree

- Within one tree, a name with its number removed is unique.
- A file can then be cited by its name alone, and every search hit identifies itself.

## No version, status or date in names

- Do not add version, status or date suffixes: `-v2`, `-r3`, `-old`, `-final`, `-superseded`,
  `-2026-10-05`.
- Where a document sits says what stage it is in. Dated records keep their dates inside the
  page, not in the name.
- Git history keeps earlier versions.

*Why:* a suffix goes stale the moment the document changes stage, and then the name lies.

## Where the other rules live

- Numbers: [21-numbering-rules.md](21-numbering-rules.md).
- Uppercase and root files: [15-uppercase-and-root-files.md](15-uppercase-and-root-files.md).
- Index contents: [23-index-format.md](23-index-format.md).
- Header fields: [25-header-fields.md](25-header-fields.md).
- Split, merge and grouping thresholds: [22-split-and-merge-thresholds.md](22-split-and-merge-thresholds.md).
