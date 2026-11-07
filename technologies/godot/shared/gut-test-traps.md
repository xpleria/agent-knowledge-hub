# GUT test-framework traps (technology: Godot 4.x with GUT, facet: shared, observed on 4.7)

- **Scope:** Technology Godot, facet shared (applies to every facet): which GUT test-framework and test-runner behaviours have caught a Godot project out, and what is the safe pattern for each?
- **Keywords:** GUT, gut test, risky test, assertion, static, teardown, after_each, await frame, orphan node, source-slicing, timed test, fake clock, injected clock, script count, parse check, --check-only, headless, test_*.gd
- **Status:** current
- **Updated:** 2026-11-07
- **Sources:** distilled from a Godot 4.7 project's test-harness notes and failed-test write-ups; GUT and engine behaviour should be re-checked on other versions

A GUT test can pass while asserting nothing, leak state into the next test, or drop out of the run. These traps are about making a green result mean that the assertions ran.

1. **Restore every global static a test changes.** Runtime statics outlive the helper that set them. A static left at a test value fails unrelated tests that run later. Reset each static the test touches in the teardown, including the ones a helper set on the test's behalf.

2. **Never guard the only assertion with `if x != null:`.** GUT then marks the test risky, because it asserts nothing, and the guarantee is silently off. Assert unconditionally, or first assert the structure that must exist, so a missing value fails the test.

3. **A source-slicing test breaks silently.** A test that reads script text between two named functions gets a negative span when a refactor reorders those functions, and the check can pass on nothing. Anchor each end independently and assert that the span is positive.

4. **Await one frame before freeing a UI test's screen.** A screen freed at once leaves nodes that GUT reports as orphans, and a later test can inherit live nodes. Make each UI test's teardown await one frame before it frees the screen it built. A clean teardown is part of the test's result: orphan warnings mean the run is not clean.

5. **A timed test drives its own clock.** A test that reads real frame time through a process callback fails intermittently with the machine's frame rate. Inject the clock, freeze the live process callback before the test's first await, and advance the test's own clock by exact amounts.

6. **The runner reconciles the script count with the files on disk.** A parse error drops a test file without a failed test, so the total simply falls. Parse-check every script with `godot --headless --check-only --script <file>`, and compare the number of scripts GUT reports with the number of `test_*.gd` files on disk. A mismatch fails the run.

## Related

- A JSON engine error counts as a GUT failure: see [gdscript-async-and-parse-traps.md](gdscript-async-and-parse-traps.md), item 5.
- A parse error drops a file from the run: see [godot-ui-traps.md](../game-client/godot-ui-traps.md), item 22.
- Test design from the rule text, and never-passing assertions: see [practices/test-design.md](../../../practices/test-design.md).
