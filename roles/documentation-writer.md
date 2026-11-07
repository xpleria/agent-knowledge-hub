# Documentation writer: settled facts, tracked work, owner decisions

- **Scope:** What does a documentation writer record as settled fact, what waits for owner acceptance, and how are owner decisions recorded without quoting the owner?
- **Keywords:** documentation writer, docs, agent-docs, progress file, pending list, acceptance, awaiting owner check, neutral wording, decision date, quote conversion, proposed, decided, pointer stub, horizon, open question, status wording
- **Status:** current
- **Updated:** 2026-11-07
- **Sources:** distilled from a Godot project's documentation runs; structure in `project-setup/10-docs-and-agent-docs-structure.md`; lifecycle in `project-setup/30-lifecycle-and-acceptance.md`

## Timing

- Update the progress file of the work item in the same session as the work. Status lives only there.
- A behaviour change outside an open forge topic updates the settled-facts docs in the same change. Inside an open forge topic, list the pending docs update in the progress file, and apply it once the owner accepts the item.
- Record `implemented + deployed, awaiting owner check` as an entry in the progress file's standing list, never as a Status value, until the owner speaks.
- Close a topic by writing its thin chronicle entry before deleting the forge folder: closed date, sign-off reference, where facts and lessons went, deferred links and one commit range. Everything else is shed; git keeps it. Correct a written entry only by a dated note at its end, never by rewriting it. Transitions for partial acceptance, deferral and cancellation: see `project-setup/32-transitions.md`.

## Recording owner decisions

- Permanent pages state an owner decision in neutral words, with the decision's date where the date is part of the record. They never quote the owner. See `practices/owner-words-in-docs.md`.
- Owner quotes belong only in transient docs (forge, horizon, briefs). At close-out, convert each quote to a neutral statement, then delete the quotation marks, before the chronicle entry is written.
- Record each sign-off in the Sign-off field of its record, in the form set by `project-setup/31-sign-off-rules.md`: the date and a reference (message, link, commit or PR). A quote may serve as the reference only in transient pages. If unsure whether a statement was a sign-off, ask the owner; never infer it.
- Keep "works", "fixed", "looks good" and "confirmed" as what they are. None of them is "accepted" unless the owner says accepted.
- Keep accepted items, items awaiting an owner check, and unconfirmed sub-questions in separate lists. An unconfirmed sub-question must not inherit its parent's acceptance.
- Keep "proposed" and "decided" apart. A proposal carries its reasoning; a decision is only what the owner said.

## Writing facts

- Write only what you verified in the code or the source, reading the cited file first. Otherwise record it as "to verify" (see [../project-setup/39-claim-verification.md](../project-setup/39-claim-verification.md)).
- Cite `path` plus the symbol or heading, not only a line number, because line numbers go stale.
- One fact per file, short pages. Split a file that answers two questions.
- When an item moves from horizon to an active forge topic, delete the horizon item and fix its inbound links in the same change, and update both indexes. Leave no pointer stub.
- Do not link settled-fact docs to work-tracking files. The link runs one way only.
