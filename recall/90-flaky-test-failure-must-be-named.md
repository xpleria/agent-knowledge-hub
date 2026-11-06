# Flaky test failure must be named

- **Scope:** How should an agent report a test that failed in a full run and then passed on a rerun?
- **Keywords:** flaky, intermittent, failing test, test name, full suite, rerun, output file, unexplained, recur
- **Status:** current
- **Source project:** ganvchi-court

## What happened

A full test run showed a failure. The agent called it flaky and moved on without recording
which test had failed. Later the same failure returned and nobody could tell whether it
was the same fault.

## Lesson

- Save the full suite output to a file on every run.
- Record each failing test by its name. A failure count alone does not explain it.
- On a failure, rerun, and record whether the same name recurs.
- Call a test flaky only with its name and the rerun results. Otherwise say "unexplained".

## Why

An unnamed failure cannot be linked to its cause, and a real regression can hide behind a
label that was used to dismiss an earlier one.
