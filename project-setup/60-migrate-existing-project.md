# Migrating an existing project into the two trees

- **Scope:** Which starting situation does an existing project have, and which migration path applies to it?
- **Keywords:** migrate, migration, existing project, case A, case B, case C, case D, Phase 0, classify, loose documentation, PLAN.md, TODO.md, NOTES.md, notes, wiki, design, stop and ask
- **Status:** current
- **Updated:** 2026-11-07
- **Sources:** the owner's lifecycle prompt, sections 5 (Phase 0) and 6, merged into this hub 2026-11-07; [15-uppercase-and-root-files.md](15-uppercase-and-root-files.md)

Rule first: a migration is read-only until the owner approves its proposal. Nothing is moved, renamed, rewritten or deleted before that.

The procedure runs in six pages: this one (Phase 0); [62](62-migration-inventory-and-proposal.md) (Phases 1 and 2); [63](63-migration-execute.md) (Phase 3); [64](64-migration-verify.md) (Phase 4); [65](65-agent-instruction-section.md) (the agent-instruction section, used in Phases 2 and 3); and [66](66-migration-report-and-obligations.md) (Phase 5 and standing obligations).

## Phase 0: classify the starting situation

| Case | Situation | Path |
| --- | --- | --- |
| A | Neither `docs/` nor `agent-docs/` exists. | Bootstrap ([40-bootstrap-checklist.md](40-bootstrap-checklist.md)). Run Phases 1 and 2 only to find loose documentation. |
| B | Only `docs/` exists. | Migrate `docs/`. Status and plans found inside it seed `agent-docs/`. |
| C | Only `agent-docs/` exists, or an equivalent notes folder. | Migrate it. Verified current facts found inside it seed `docs/`. |
| D | Both exist. | Migrate both, and enforce the boundary ([10-docs-and-agent-docs-structure.md](10-docs-and-agent-docs-structure.md)) in both directions. |

Name the case in the proposal.

## Loose documentation

- Look for root `PLAN.md`, `TODO.md`, `NOTES.md`, CHANGELOG-like status files, `notes/`, `wiki/`, `design/` and similar. They are inputs to classify, not files to keep as they are (see [15-uppercase-and-root-files.md](15-uppercase-and-root-files.md)).
- Conventional files (`README.md`, `LICENSE`, `CONTRIBUTING.md`, `CHANGELOG.md`) and agent files (`AGENTS.md`, `CLAUDE.md`, `IDEA.md`, or any file an agent loads by name) stay where they are. If you are unsure whether a root file is an agent file, ask the owner.

## Before starting

- Run `git status` and note the branch. If someone else's work is uncommitted, or another person or agent is actively writing in these trees, stop and ask (see [45-git-rules.md](45-git-rules.md)).
- Read the project's agent-instruction files and any existing convention text. They are inputs. Conflicts with this procedure go into the proposal.
- Never read, print or move credential files (see [50-deploy-and-verify-habits.md](50-deploy-and-verify-habits.md), "Secrets").
