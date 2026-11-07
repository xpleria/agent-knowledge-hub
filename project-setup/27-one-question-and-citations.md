# One question per file and citations

- **Scope:** How many questions may one file answer, how are headings and statement kinds kept apart, and how is code cited?
- **Keywords:** one question, one fact, headings, disambiguating nouns, retrieval, statement kinds, decision vs measurement, normative vs descriptive, rationale vs procedure, fact vs status, code citation, path, symbol, line anchor, re-check
- **Status:** current
- **Updated:** 2026-11-07
- **Sources:** the owner's lifecycle prompt, section 2.5 (writing for retrieval); the hub's `AGENTS.md` one-fact-per-file rule

Rule first: one file answers one question. If a page answers two separable questions, split it
(thresholds are in [22-split-and-merge-thresholds.md](22-split-and-merge-thresholds.md)).

## Headings

- Repeat the disambiguating noun in each heading, so a chunk retrieved alone still says what
  it is about: "Card-sizing constants", not "Constants".
- A heading that could sit unchanged under two different topics needs the noun added.

*Why:* retrieval returns a section, not a whole page. A section without its noun is ambiguous.

## Statement kinds

Keep these kinds of statement in separate files:

- decision vs measurement;
- normative vs descriptive;
- rationale vs procedure;
- fact vs status.

*Why:* each kind has a different owner, a different rate of change and a different way of
going stale. A decision that sits next to a measurement reads as if the measurement settled it.

## Citing code

- Permanent pages (docs, lore, hub) cite code as `path` plus the symbol or heading. No line numbers.
- Transient pages (forge, horizon, evidence) may cite `path:line`.
- Prefer the symbol wherever one exists, even in transient pages. Line numbers go stale.
- Re-check every cited anchor whenever the cited file changes.

*Why:* a stale anchor sends the reader to the wrong code with full confidence.

## Links

- Use relative links that resolve from the file's own location.
- Cross-link rather than duplicate. Each fact has one home, and every other page links to it.
