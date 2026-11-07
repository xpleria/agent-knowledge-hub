# Implementer: measure first, then check the traps

- **Scope:** What must an implementer measure and check before calling a change done, and which traps does the generic loop not spell out?
- **Keywords:** implementer, reproduce, measure, failing test first, mutation check, fresh build, relayout, input, modal, layer, pointer events, wall-clock lock, protected files, tooling, discard, stash
- **Status:** current
- **Updated:** 2026-11-07
- **Sources:** distilled from a Godot project's implementation runs; engine specifics are in `engines/`; see `recall/` for the scenarios behind each rule

## Loop

1. Start from a clean base on a feature branch. Never lose uncommitted work.
2. Reproduce first. Write a test that fails on the current code and passes after the fix.
3. Test the end user's effect, not a flag or an internal signal.
4. If the defect does not reproduce, do not guess a fix. Report the device steps you would need.
5. Run the full suite, saving its output to a file so failing names survive.
6. Commit each item separately, before any deploy, when commits are permitted. Otherwise leave the changes uncommitted and say so.

## Measure before and after

- Print the relevant sizes or positions before the fix and after it. A fix without a before-number cannot be checked.
- Re-anchor any value placed outside a layout container in the layout path. One-shot placement breaks on resize and rotation.
- For a relayout, compare the result with a fresh build at the same size, control by control. See `recall/50-relayout-must-equal-fresh-build.md`.

## Input and overlays

- Give each modal its own top-level layer above the content. Ordering within one layer is not enough.
- Absorb every pointer press and release until all pointers are up, not only the first.
- Make input locks depend on wall-clock time, not on a scaled or animated time.
- Classify dialogs as user-triggered or game-triggered. Ask the owner before mapping a key to a consequential button.

## Scope and tooling

- Fix only what the owner asked for. Report adjacent findings separately.
- Decide where each rule is enforced: the rules layer, the UI, or automation. Actors other than the UI must go through the same check.
- Never run recursive deletes or chained one-liners in a subagent brief. Use the file tools and plain single commands. See `recall/20-auto-denied-recursive-delete-stopped-run.md`.
- Discard nothing with `git checkout`, `git restore` or `git reset`. Use `git stash push -u -m <name>`.
- Do not edit protected instruction files. Report the needed change to the orchestrator.
