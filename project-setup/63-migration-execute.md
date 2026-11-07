# Migration execution after owner approval

- **Scope:** In what order does an approved migration create the skeleton, move, weave, relocate and re-point files?
- **Keywords:** execute, skeleton, git mv, pure renames, weave, split, merge, shed, helpers, relocate, inbound references, conventions, agent-instruction section, commit, transitions, Phase 3
- **Status:** current
- **Updated:** 2026-11-07
- **Sources:** the owner's lifecycle prompt, section 5 (Phase 3), merged into this hub 2026-11-07; [45-git-rules.md](45-git-rules.md); [36-lore-rules.md](36-lore-rules.md)

Rule first: execute only what the owner approved, and keep each rename commit apart from content edits.

## Steps

1. **Skeleton.** Create the tree roots, the stage and tier folders, and their indexes, with headers.
2. **Move and rename** with `git mv`. Content edits come after the moves. If commits are permitted, commit each rename as a rename commit: the `git mv` plus only the link repoints that the rename breaks. Then commit the content edits separately (see [45-git-rules.md](45-git-rules.md) and [practices/commit-granularity.md](../practices/commit-granularity.md)).
3. **Weave.** Split, merge and rewrite into the target files, add headers, and shed dead material (see [36-lore-rules.md](36-lore-rules.md)). Normative text in `docs/` changes in meaning only with explicit owner approval.
4. **Helpers.** Relocate kept helpers to the tooling folder, delete throwaway helpers, and exclude or ignore sidecars (see [37-evidence-and-helpers.md](37-evidence-and-helpers.md)).
5. **References.** Update every inbound reference from the Phase 1 list: docs, agent files, code comments, tests, tooling and CI. Code comments cite `docs/` facts, never `agent-docs/` paths.
6. **Conventions.** Write the conventions into `docs/README.md` (see [18-conventions-location.md](18-conventions-location.md)), the lifecycle rules into `agent-docs/README.md`, and the agent-instruction section (see [65-agent-instruction-section.md](65-agent-instruction-section.md)).
7. **Transitions.** Perform each approved transition in the same session as its sign-off (see [32-transitions.md](32-transitions.md)). Write a closed topic's chronicle entry before its forge folder is deleted.

## Limits

- Commit only when the owner or the project permits commits. Never push or deploy unless the owner asks.
- Never read, print or move secrets or credential files.
- Do not fix a conflict on either side. Record it (see [38-code-versus-docs.md](38-code-versus-docs.md)).
- A forge topic created for this migration needs the owner's commencement sign-off first.
