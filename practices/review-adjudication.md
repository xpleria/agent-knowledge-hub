# Review adjudication: a claim is a hypothesis until checked

- **Scope:** How do I judge a reviewer's claims, review notes and progress reports, so that a wrong claim is caught and progress is not inflated?
- **Keywords:** review, reviewer, adjudicate, hypothesis, verdict, anchor, alternative, review note, point, measurement, ratio, progress, line count, placeholder, score zero, percentage, component table
- **Status:** current
- **Updated:** 2026-11-07
- **Sources:** distilled from a Godot project's review rounds and progress analyses; see also `practices/measurement-and-probes.md`

Rule first: a reviewer's claim is a hypothesis; it is adopted only after a check against a measurement or the rule text.

## Judge each claim

- Check each claim against a measurement or the governing rule before adopting or rejecting it. In one review of ten claims, seven held, two were refuted by measurement, and one real defect was missed by the probe.
- Adjudicate point by point. Give each point a verdict: accepted, accepted with modification, or declined, with the governing file or measurement. Do not adopt a review wholesale, and do not reject one on taste.
- Check the ratio between verified numbers, not only each number. A reviewer checked each figure, found each plausible, and missed the defect that lay in the relation between them.
- A disagreement with a measurement names that measurement.

## Write a review note

Each point in a review note has four parts:

- **Point:** what is claimed, in one sentence.
- **Verdict:** accepted, accepted with modification, or declined.
- **Anchor:** the file and line in a transient note, or the file and symbol in a permanent page (see [project-setup/38-code-versus-docs.md](../project-setup/38-code-versus-docs.md)).
- **Alternative:** the concrete change proposed instead.

A note that says a layout "looks wrong" without a control, a line and an alternative cannot be verified or acted on.

## Measure progress by weight, not by count

- Progress is not line count. Weight each component by how much it blocks the product and what it costs to retrofit later.
- Show the per-component table as the result. A single percentage compresses independent judgements and can hide the fix that matters most.
- A placeholder, such as an empty test folder or a config entry with no test, is an intention. Score it zero.

*Why:* a review accepted without checks propagates its errors, and a percentage that rises with line count rewards volume over the fix that blocks the owner.
