# Test design: assert the rule, not the current behaviour

- **Scope:** What should a test assert, so that a green run means the rule holds, and which assertions can pass by accident?
- **Keywords:** test design, rule text, oracle, assertion, specific outcome, disjunction, positive path, guard, conservation invariant, floor, threshold, value, false pass
- **Status:** current
- **Updated:** 2026-11-07
- **Sources:** distilled from a Godot project's test-design lessons; see `practices/test-harness-and-inputs.md` for harness and fixture rules

Rule first: a test states what the rule requires, so a wrong implementation fails it.

## Take the oracle from the rule

- Write each test from the rule text, not from what the code does now. A test that records current output stays green while the output is wrong.
- Why: one project's suite stayed green with nine decision-changing defects live, because its tests asserted engine output.
- If a test's name and its assertion disagree, fix the one that is wrong. A name that promises a rule the assertion does not check is a false pass.
- When a name promises both halves of a rule, assert both. "Never shows others' cards" also means "shows your own".

## Assert what cannot pass by accident

- Assert the specific expected outcome. A disjunction can pass a wrong result: `debt == 0 or 6 or 52` passes on a bug that always charges the same party.
- Assert a floor or threshold as its value. "No scale below 1.0" still passes when the floor is 0.5; assert that the constant equals 1.0.
- Every guard needs a positive-path test that shows the action can be accepted. A type error inside a guard can look like an ordinary refusal and hide the defect.
- Use a conservation invariant over patching the same function again. For example, a per-round census of every card, counted once each, catches a whole class of defects.
- Never guard the only assertion with a condition such as "if the value is not null". The test then asserts nothing and passes silently.

## Why this matters

A passing suite proves only what its assertions check. An assertion written from the code confirms the code, not the rule, so its green result is no evidence that the rule holds.

*See also:* [evidence-and-verification.md](evidence-and-verification.md) for how a suite result is reported.
