# Docs and agent-docs structure: settled facts versus work

- **Scope:** What belongs in a project's `docs/` tree and what belongs in its `agent-docs/` tree?
- **Keywords:** docs, agent-docs, settled facts, normative, descriptive, authority order, lore, forge, horizon, work lifecycle, boundary, one-way links
- **Status:** current
- **Sources:** distilled from a Godot project's `docs/README.md` and `agent-docs/README.md` (ganvchi-court)

Every project keeps two trees, separated by one boundary.

## `docs/`: settled facts only

- Holds facts that are settled: what must be true (normative) and what the code and tooling do now (descriptive).
- Never holds status, plans, proposals, open questions or "not yet built" notes.
- Tiers run in authority order, numbered so the reading order is visible, for example:
  rules, requirements, architecture, development, testing, decisions, implementation notes.
- A higher tier governs a lower one. The lowest tier, implementation notes, describes and
  never overrides.
- A normative change is made only by the project owner. A descriptive file that no longer
  matches the code is a defect.

## `agent-docs/`: the work lifecycle

- `lore/`: lessons, rationale and pitfalls from finished or cancelled work. A living record:
  replace obsolete statements, delete dead ones.
- `forge/`: active work, one topic folder per workstream. Status lives only in the topic's progress file.
- `horizon/`: future work nobody has committed to yet.
- Grow the tree by subject, not by date. A folder that answers one question stays a single file.

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
