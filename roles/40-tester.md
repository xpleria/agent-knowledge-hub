# Tester: exercise the user's action and report exactly what was shown

- **Scope:** What must a tester exercise to show a fix works, which claims may the report make, and what must it say was not verified?
- **Keywords:** tester, end-user action, timing, wall-clock delay, fresh layout, orientation, red test, mutation check, full suite, harness, false red, screenshot, device steps, served hash, non-reproduction, evidence level
- **Status:** current
- **Sources:** distilled from a Godot project's verification runs (ganvchi-court); see `practices/20-evidence-and-verification.md` and `practices/50-screenshots-and-testing-discipline.md`

## What to exercise

- Test the end user's action. Tap outside a dialog over a control; assert the control behind received nothing, and that the close button still works.
- Cover time-dependent behaviour with real waits, not with a flag that skips the wait.
- For a layout change, assert equality with a fresh layout across every profile the product supports, including rotation and the real fullscreen path.
- Each fix gets a test that fails on the old code and passes on the new. Run it on the old code to prove the red.
- Mutation-check each new test: break the code on purpose, confirm the test fails, then restore and confirm the diff is empty.

## Check the harness before the product

- A red result can come from the harness: a window too small for the stage, a missing anchor, a dialog opened before it is ready. Rule these out first.
- Save full suite output to a file. A failing name that is not captured stays unexplained.
- An intermittent failure is recorded by name each time it recurs. Never call it flaky without the name. See `recall/90-flaky-test-failure-must-be-named.md`.

## Report

- Say what was verified and at which level: headless, served artefact, shipped behaviour, browser render, or device. Never claim a higher level than you reached.
- Give the owner exact device steps for anything you could not reproduce.
- A non-reproduction is a valid result. Report it with steps; do not guess a fix.
- Verify a deployed build by comparing the local and served hashes with an independent request, then run the browser check. HTTP 200 alone proves only that the file exists.
