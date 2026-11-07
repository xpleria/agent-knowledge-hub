# Docs and agent-docs structure: settled facts versus work

- **Scope:** What belongs in a project's `docs/` tree and what belongs in its `agent-docs/` tree?
- **Keywords:** docs, agent-docs, settled facts, normative, descriptive, authority order, lore, forge, horizon, chronicle, work lifecycle, boundary, one-way links
- **Status:** current
- **Updated:** 2026-11-07
- **Sources:** distilled from a Godot project's `docs/README.md` and `agent-docs/README.md`

Every project keeps two trees, separated by one boundary.

## `docs/`: settled facts only

- Holds facts that are settled: what must be true (normative) and what the code and tooling do now (descriptive).
- Never holds status, plans, proposals, open questions or "not yet built" notes.
- Tier folders, their authority order and the change rules for each tier are set out in
  [12-docs-tiers-and-glossary.md](12-docs-tiers-and-glossary.md).

## `agent-docs/`: the work lifecycle

- `01-lore/`: lessons, rationale and pitfalls from finished or cancelled work. A living record:
  replace obsolete statements, delete dead ones.
- `02-forge/`: active work, one topic folder per workstream. Status lives only in the topic's progress file.
- `03-horizon/`: future work nobody has committed to yet.
- `04-chronicle/`: a thin register, one page per closed forge topic: its closed date, its
  sign-off, where its facts (docs) and lessons (lore) went, its deferred items (horizon
  links) and one commit range, plus an optional short "What shipped" paragraph for developers.
  It holds no commit lists, round logs or narrative, and it is not a published changelog.
- Grow the tree by subject, not by date. A folder that answers one question stays a single file.
- The stage folders are numbered 01 to 04 in lifecycle order. Each has a `00-<stage>-index.md`.

## Boundary rules

- `docs/` never links into `agent-docs/` and never names a file there as a source. Facts
  must not depend on work in progress.
- `agent-docs/` may link into `docs/`.
- Code comments cite `docs/` facts, decision IDs or commits, never `agent-docs/` paths,
  because work-tracking paths move.
- Neither tree holds runnable code, generated files or engine sidecars. A useful probe
  lives in the project's tools folder.

## Small projects

If a project has few facts or one workstream, keep the same two-tree split but collapse
folders that hold one file into that file. Do not drop the boundary.
