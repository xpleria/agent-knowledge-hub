# <Project name> agent instructions

Instructions for AI agents working in this repository.

## Project

<One paragraph: what the project is, its target platforms, and the hard constraints
an agent must never break.>

## Documentation is the source of truth

- Read `docs/README.md` first. Facts are in `docs/`; work tracking is in `agent-docs/`.
- Read the tier files the task touches, in authority order, and stop once the question is answered.
- Before a task, check `agent-docs/forge/00-forge-index.md` for an active topic. Continue it; never start a parallel one.
- Never infer a rule from code when `docs/` states it. If they disagree, the code is wrong. If the rules are ambiguous, stop and ask the owner.

## Work tracking

- A topic moves only after the owner signs off. Passing tests are not sign-off.
- Docs are updated once, after the owner accepts the item. The pending update lives in the progress file.
- Record the owner's words verbatim and do not upgrade them to "accepted".

## Working practices

- Inspect existing code first; match its structure. Make the smallest change that solves the task.
- Every behaviour change ships with a test in the same change.
- Local commits only unless the owner asks to push. Never discard work with `git checkout`, `git restore` or `git reset`; use `git stash push -u -m <name>`.
- One writing agent per working tree at a time.
- Credentials are never printed, committed or passed as arguments.

## Cross-project knowledge hub

<Owner decision: insert the paragraph from the hub's README or from the owner's brief.
Name the hub path, say agents recall from `recall/` by keyword and consult `roles/`,
`practices/` and `project-setup/` for their role and for setup.>

## Definition of done

The change compiles, the full test suite passes with its output saved, the change is
covered by a test that failed before it, the documentation matches the code, and any
deploy has been verified by hash and by the browser or device check.
