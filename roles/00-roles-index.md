# Roles index

- **Scope:** Which role-specific guidance applies to the role an agent holds, and which page to read for it?
- **Keywords:** roles, orchestrator, implementer, documentation writer, tester, subagent, delegation, role, handoff, evidence
- **Status:** current
- **Sources:** distilled from a Godot project's agent role lessons (ganvchi-court, `agent-docs/01-lore/90-agent-roles/`), generalised to be project-agnostic

One agent may hold several roles. Read the page for each role you hold. A subagent that
was briefed for one job usually holds one role, and its brief names it. Project rules
(in the project's `AGENTS.md`) always override these pages.

## Reading guide

- **Orchestrator** (splits work, briefs and checks subagents, relays owner questions):
  read [10-orchestrator.md](10-orchestrator.md).
- **Implementer** (changes code or configuration): read [20-implementer.md](20-implementer.md).
- **Documentation writer** (edits project docs and work-tracking files):
  read [30-documentation-writer.md](30-documentation-writer.md).
- **Tester** (writes tests, captures evidence, verifies deploys): read
  [40-tester.md](40-tester.md).

## Children

| File | What question it answers |
| --- | --- |
| [10-orchestrator.md](10-orchestrator.md) | How do I brief, sequence, verify and report on delegated work without collisions or over-claims? |
| [20-implementer.md](20-implementer.md) | What must I measure and check before calling a change done? |
| [30-documentation-writer.md](30-documentation-writer.md) | What do I record now, what waits for acceptance, and how are owner words kept exact? |
| [40-tester.md](40-tester.md) | What must I exercise, which claims may my report make, and what must it say was not verified? |
