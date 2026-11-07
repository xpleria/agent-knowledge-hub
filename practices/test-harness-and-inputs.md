# Test harness and inputs: drive the rules, do not fake coverage

- **Scope:** How should a test harness drive the product, and which fixtures and random inputs count as coverage?
- **Keywords:** harness, driver, helper, waiting on, local actor, staged fixture, hand played, coverage, randomness, injected seed, construct the deal, automated actor, projection, hidden information, same view
- **Status:** current
- **Updated:** 2026-11-07
- **Sources:** distilled from a Godot project's test-harness and audit lessons; see also `practices/test-design.md`

Rule first: a harness asks the rules whose turn it is; it never assumes.

## Drive the rules, not an assumption

- A helper acts only when the rules say it is that actor's turn. A helper that acts for the local actor unconditionally let a live defect pass the whole suite.
- Use the rules' own query for what each seat is waiting on, and let that answer choose the actor.
- Validate a harness input before you record a defect against the product. A probe that plays a card the seat does not hold reports a defect the product does not have.

## Fixtures are not coverage

- A staged fixture with no hand played through it is not coverage. Independent audits found blockers the suite had missed.
- Pair each staged fixture with at least one test that reaches the same state through the real action path.
- A fixture that assumes a synchronous step can break when that step becomes paced or asynchronous. Re-check fixtures when the timing model changes.

## Randomness and fixed inputs

- Inject randomness; never call the random source inside rules code.
- Construct the state a test needs rather than searching seeds until one happens to fit. A searched seed hides the case it was meant to test.
- Record the seed or the constructed state with the test result, so a failure can be reproduced.

## Automated actors see what humans see

- An automated actor receives the same projection as a human at the same seat. It must never receive state the human could not see.
- Test this with an assertion: the automated actor's view equals the human's view at that seat.

*Why:* a harness that bends the rules, or a fixture that skips the path a player takes, makes the suite pass for a product that players cannot reach.
