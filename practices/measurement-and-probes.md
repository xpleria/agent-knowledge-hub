# Measurement and probes: a number must be able to be wrong

- **Scope:** How do I measure a layout or behaviour so that the number describes a state a user reaches, and the measurement could have failed?
- **Keywords:** probe, measurement, baseline, reproduce, override, recomputed, silently ignored parameter, attribution, 2x2, combined change, base commit, detached worktree, regression, text measurement, geometry, image
- **Status:** current
- **Updated:** 2026-11-07
- **Sources:** distilled from a Godot project's probe and capture lessons; see also `practices/screenshots-and-testing-discipline.md`

Rule first: a probe that cannot fail proves nothing, so check that it could report a failure before trusting its number.

## Make the probe able to fail

- A probe that reads its result after the state has settled cannot fail. Check that it would report the defect on the old code.
- Do not force a state that a user never reaches. A forced recalculation can measure a state the product never enters; wait the way the product waits.
- A probe that finds nothing on a screen that visibly has something is broken, not exonerating. Find out why before reading a zero.
- Check each probe output against a known value before using it. A value the probe was not told to check says nothing about that value.

## Reproduce before you change

- Reproduce the baseline on the unmodified tree before editing. If the numbers differ from the recorded evidence, stop and report.
- Confirm the measured value is the one the product uses. An injected override that the product recomputes is not an override: one probe set a device value that the product reset, so twelve cases all measured one device.
- A harness parameter that is silently ignored invalidates every number that depends on it. Check that each parameter reaches the code under test.

## Attribute the result

- Measure each change alone and combined. Use a 2x2 when two changes interact; one number for several changes misattributes the effect.
- Prove "not a regression" on the base commit. Re-run the check on a detached worktree at the base; a defect that already exists there is not caused by your change, and it stays out of your change.
- Record a result you cannot reproduce as unreproduced. Do not attribute it to a fix.

## Prefer text to images

- Prefer text or geometry measurements to images. They are repeatable; a reading from an image is not.
- Use a vision reading for text only, and check its size against a measurement.

*Why:* an unfalsifiable probe turns a bug into a green number, and a number without its baseline cannot be checked by anyone else.
