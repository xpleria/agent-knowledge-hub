# <Project name> agent instructions

<!-- Hub template: project-setup/templates/10-agents-md-template.md. Placement, verbatim copies and reconciling existing text: project-setup/65-agent-instruction-section.md. Verbatim copies of this file: <paths, or none>. -->

## Project

<One paragraph: what the project is, its target platforms, and the hard constraints an agent must never break.>

## Working practices

- Inspect existing code first and match its structure. Make the smallest change that solves the task.
- Every behaviour change ships with a test in the same change.
- Commit only when the owner or this file permits commits; then commit locally, one logical change per commit. Never push unless the owner asks.
- Never discard work with `git checkout`, `git restore` or `git reset`. Use `git stash push -u -m <name>`.
- One writing agent per working tree at a time.
- Ask the owner before a consequential choice. If a rule is ambiguous, stop and ask.
- Owner decisions go into permanent docs in neutral words. Quote the owner only in transient docs (forge, horizon, briefs).
- Secrets, two scopes: documentation and migration work never reads, prints or moves credential files. The deploy script reads its gitignored env file as data; it never prints it, sources it, or passes secrets as arguments.

## Documentation and work tracking

<!-- Canonical section: found by this heading, updated in place, never duplicated. Full rules: docs/README.md ("Documentation conventions") and agent-docs/README.md. -->

- **`docs/` holds settled facts:** normative (rules, requirements, accepted decisions) and descriptive (what the code, tests and tooling do now). Never status, plans or proposals. Tiers in authority order: `<01-…/>`, `<02-…/>`, and so on. A higher tier governs a lower one.
- **`agent-docs/` holds the work lifecycle:** `01-lore/` lessons (living; obsolete statements are replaced), `02-forge/` active topics (status only in each progress file), `03-horizon/` future work, `04-chronicle/` a thin register of closed topics.

Before a task: read `docs/README.md` and the tier files the task touches; check `agent-docs/02-forge/00-forge-index.md` for an active topic covering it, and continue that topic; check `agent-docs/01-lore/00-lore-index.md` for lessons in the subject area.

During and after a task: a behaviour change updates the matching `docs/` fact in the same change, unless it sits inside an open forge topic. Then the update waits for acceptance, under "Pending docs update" in the progress file. Work on a forge topic updates its progress file in the same session. Topics move only on the owner's sign-off of the work, in the same session, by the transitions in `agent-docs/README.md`. Record the sign-off in the topic index. Passing tests and your own judgement are not sign-off. Verify a claim against code or tests before it enters `docs/`; otherwise record it as "to verify".

Naming: `NN-topic-slug.md` and `NN-topic-slug/`; numbers are reading order; every folder has `00-<slug>-index.md`; evidence sits in `99-<slug>-evidence/`; no version or date suffixes. Every page opens with the Scope, Keywords, Status, Updated and Sources header. Neither tree holds runnable code, generated files or engine sidecars.

## Cross-project knowledge hub

<Owner decision: insert the paragraph from the hub's README or from the owner's brief. Name the hub path, say agents recall from `recall/` by keyword and consult `roles/`, `practices/` and `project-setup/` for their role and for setup.>

## Definition of done

The change compiles, the full test suite passes with its output saved, the change is covered by a test that failed before it, the documentation matches the code, and any deploy has been verified by hash and by the browser or device check.
