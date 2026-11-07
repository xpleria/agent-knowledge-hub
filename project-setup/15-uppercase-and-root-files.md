# Uppercase names and root files

- **Scope:** Which files keep uppercase names, and how is an unfamiliar root file classified before it is treated as documentation?
- **Keywords:** uppercase, README.md, AGENTS.md, CLAUDE.md, IDEA.md, LICENSE, CONTRIBUTING.md, CHANGELOG.md, root file, agent file, conventional name, loose documentation, PLAN.md, TODO.md, NOTES.md, notes, wiki, design
- **Status:** current
- **Updated:** 2026-11-07
- **Sources:** the owner's lifecycle prompt, section 2.1 (names and exceptions) and its Phase 0 root-file check

Rule first: only conventional and agent-loaded files keep uppercase names. Every other file
and folder name is lowercase and hyphen-separated.

## Files that keep their names

- `README.md`: at each tree root (`docs/`, `agent-docs/`) and at the repository root. It is
  the entry file of its tree.
- `AGENTS.md` and `CLAUDE.md`: agent instruction files.
- `IDEA.md`: an agent project-description file.
- `LICENSE`, `CONTRIBUTING.md` and `CHANGELOG.md`: conventional repository files.

These files keep their names and their locations. A migration never moves, renames or sheds
them.

*Why:* tools and people find these files by name. Renaming one breaks the load path, so the
uppercase form marks the files that must stay as they are.

## Before treating an unfamiliar root file as documentation

1. Check whether an agent or a tool loads the file by name.
2. If one does, it is an agent file. A migration re-paths its stale references only, and it
   reports any conflict with the other agent files.
3. If you cannot tell whether a root file is an agent file, ask the owner. Do not guess.

## Loose documentation elsewhere

- Loose documents outside the two trees (for example `PLAN.md`, `TODO.md`, `NOTES.md`,
  `notes/`, `wiki/`, `design/`) are inputs to classify. They are not kept as they are.
- Each one is classified as a fact (to `docs/`), lore, forge, horizon, or shed.

*Why:* loose files hold status and plans that drift from the code. Classifying them once,
at migration, stops them from becoming a second source of truth.
