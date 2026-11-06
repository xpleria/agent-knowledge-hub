# Roles index

- **Scope:** Which role-specific guidance applies to the role an agent holds, and which page to read for it?
- **Keywords:** roles, orchestrator, implementer, documentation writer, tester, subagent, delegation, role, handoff, evidence
- **Status:** current
- **Updated:** 2026-11-03
- **Sources:** distilled from a Godot project's agent role lessons (ganvchi-court, `agent-docs/01-lore/90-agent-roles/`), generalised to be project-agnostic

One agent may hold several roles. Read the page for each role you hold. A subagent that
was briefed for one job usually holds one role, and its brief names it. Project rules
(in the project's `AGENTS.md`) always override these pages.

## Reading guide

- **Orchestrator** (splits work, briefs and checks subagents, relays owner questions):
  read [orchestrator.md](orchestrator.md).
- **Implementer** (changes code or configuration): read [implementer.md](implementer.md).
- **Documentation writer** (edits project docs and work-tracking files):
  read [documentation-writer.md](documentation-writer.md).
- **Tester** (writes tests, captures evidence, verifies deploys): read
  [tester.md](tester.md).

## Children

| File | What question it answers |
| --- | --- |
| [orchestrator.md](orchestrator.md) | How do I brief, sequence, verify and report on delegated work without collisions or over-claims? |
| [implementer.md](implementer.md) | What must I measure and check before calling a change done? |
| [documentation-writer.md](documentation-writer.md) | What do I record now, what waits for acceptance, and where may owner words appear? |
| [tester.md](tester.md) | What must I exercise, which claims may my report make, and what must it say was not verified? |
