# Migration inventory and the owner proposal

- **Scope:** What does a migration's read-only inventory record for each file, and what must the proposal contain before the owner approves it?
- **Keywords:** inventory, kind, state, verify, inbound references, conflicts, proposal, mapping table, target tree, transitions, reference-update list, agent-instruction change, owner approval, Phase 1, Phase 2
- **Status:** current
- **Updated:** 2026-11-07
- **Sources:** the owner's lifecycle prompt, section 5 (Phases 1 and 2), merged into this hub 2026-11-07; [31-sign-off-rules.md](31-sign-off-rules.md)

Rule first: inventory every file in scope, then present the proposal and stop until the owner approves it.

## Phase 1: inventory (read-only)

For every file in scope, record:

1. **Kind:** normative fact, descriptive fact, decision (accepted or proposed), plan, progress or status, analysis or findings, lesson or rationale, open question, owner-supplied input, evidence, helper code, or generated sidecar.
2. **State:** done, active, paused, deferred or dead. Verify it against the current code and the git history. Never trust the document's own status line. Note which "done" items have a recorded owner acceptance.
3. **Inbound references** across the whole repository: other docs, agent files, code comments, tests, tooling, CI configs and scripts that write into these paths. Search for path fragments and for bare file names.
4. **Conflicts** between documents, or between a document and the code (see [38-code-versus-docs.md](38-code-versus-docs.md)).

Keep the inventory in a scratch working file. It is not a deliverable.

## Phase 2: proposal, then stop

Present to the owner:

1. **Target tree** down to topic level, with numbers and slugs.
2. **Mapping table:** one row per source file. Columns: source, destination or destinations, action (`move`, `rename`, `split`, `merge`, `weave into <topic>`, `promote to docs`, `shed`, `relocate helper to <path>`, `ignore sidecar`), reason.
3. **Transitions needing sign-off:** work that looks finished without a recorded acceptance, and work that looks abandoned. The owner accepts, defers or cancels each one, in bulk or individually. The owner's approval of these rows is the sign-off for those transitions (see [31-sign-off-rules.md](31-sign-off-rules.md)). Record it as such.
4. **Conflicts and owner decisions:** boundary questions, conflicts between this procedure and the project's conventions, contradictions found in Phase 1, and any threshold overrides you recommend. For each: the decision needed, the context, the options and your recommendation.
5. **Reference-update list** from Phase 1, item 3.
6. **Agent-instruction change** (see [65-agent-instruction-section.md](65-agent-instruction-section.md)): the exact section text, and each existing passage to be replaced, shortened or re-pathed, with its reason.

Do not proceed until the owner approves. Apply the owner's corrections and re-present only the changed rows.
