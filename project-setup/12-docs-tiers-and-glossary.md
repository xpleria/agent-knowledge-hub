# Docs tiers and glossary

- **Scope:** Which tier folders does a project's `docs/` tree use, in what authority order, and where does its glossary go?
- **Keywords:** docs tiers, tier folders, authority order, ground-truth, requirements, architecture, development, testing, user guide, decisions, glossary, renamed terms, normative, descriptive
- **Status:** current
- **Updated:** 2026-11-07
- **Sources:** the docs tier table in the owner's lifecycle prompt (section 3), generalised; a Godot project's `docs/README.md` for the normative and descriptive split

A project's `docs/` tree holds tier folders numbered in authority order. A project creates
only the tiers it needs, and only when a tier has content. Planned tiers are listed in
`docs/README.md`, not left as empty folders.

## Typical tiers

| Folder | Holds |
| --- | --- |
| `01-ground-truth/` | The domain rules or external specification the software implements, if any. |
| `02-requirements/` | What the software must do. |
| `03-architecture/` | How the software is built. |
| `04-development/` | How code is written, built, run and released (the developer guide). |
| `05-testing/` | How correctness is shown. |
| `06-user-guide/` | How the product is used. |
| `07-decisions/` | Accepted decision records, each with a permanent ID (see [21-numbering-rules.md](21-numbering-rules.md)). |
| `NN-implementation/` | Optional, usually last. Descriptive notes on what was built and measured. Lowest authority; corrected when the code moves. |

The table gives the typical position of each tier. A project fixes where its decisions tier
sits in the authority order in its `docs/README.md`.

Older hub wording (rules, implementation notes) folds into these tiers. Rules sit in
`01-ground-truth/` or `02-requirements/`, depending on whether they describe the domain or
the product. Implementation notes are descriptive. They sit in `NN-implementation/` when the project has
that tier, otherwise in `03-architecture/` or `04-development/`.

## Authority and change

- Higher tiers govern lower ones. A lower tier never changes a higher tier's meaning.
- A normative file changes only by owner decision. A migration may rename it, add its header
  and index, and fix its links, but must not change its meaning.
- A descriptive file is corrected when the code moves. A descriptive file that no longer
  matches the code is a defect, not history.

*Why:* when two files conflict, a reader needs one rule. The higher tier wins, and only the
owner moves a normative rule.

## Glossary

- The glossary is a numbered file at the `docs/` root, for example `08-glossary.md`. Its
  number comes from the docs-root sequence (see [21-numbering-rules.md](21-numbering-rules.md)),
  placed where it best serves reading order. Do not number it `00`: that number is reserved
  for an index.
- Define each term once. Every other file uses the canonical term.
- Keep a renamed-terms table in the glossary: old term, canonical term, and the reason for
  the rename.

*Why:* a term defined once and used everywhere keeps search results consistent. The
renamed-terms table lets a reader who meets an old name find the current one.
