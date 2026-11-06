# Headless window size causes false reds

- **Scope:** When a UI test fails but the product works, how do I tell a harness fault from a product fault?
- **Keywords:** headless, false red, harness, viewport, window size, SubViewport, stage, input events, dialog, ready, anchor
- **Status:** current
- **Source project:** ganvchi-court

## What happened

Input tests clicked controls and every click was dropped. The product was fine. The test
root window was far smaller than the layout it drew, so the click positions fell outside
the visible area.

## Lesson

- Before calling a red result real, check the harness: window size, anchors, and whether the screen was ready when the test acted.
- Host the screen in a stage viewport of a known size, and push real input events into it.
- Set anchors and offsets after adding a node to its parent.
- Open a dialog only after the screen's ready step has run.

## Why

A false red sends the team after a bug that does not exist, and it can hide a real one when
the test is ignored.
