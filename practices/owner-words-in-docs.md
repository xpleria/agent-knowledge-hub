# Owner questions and owner words

- **Scope:** How should an agent put a question to the owner, and where may the owner's own words appear in a project?
- **Keywords:** owner question, decision, options, recommendation, owner words, quote, neutral wording, decision date, sign-off, accepted, confirmed, works, fixed, standing list, pending, stale premise, scope change, close-out
- **Status:** current
- **Updated:** 2026-11-03
- **Sources:** distilled from a Godot project's owner-communication rules (ganvchi-court); the owner's rule of 2026-11-03 on quoting in permanent docs

## Asking

- Put each question as: the decision, the context, the options with their impact on the project, then a recommended option first.
- Batch independent questions into one message.
- Do not ask what the plan already recommends, unless the choice really is open.
- If the premise is stale, because the code or an earlier acceptance has already superseded it, say so and propose closing the question instead of asking it.
- For wording decisions, read the current strings first, then propose two or three candidates with a recommendation.
- Ask before mapping a key or button to a consequential action.

## Where owner words may appear

- **Transient docs may quote the owner verbatim:** forge topic files, horizon items, delegation briefs and working notes. Quote in quotation marks, with the date and where the words appear.
- **Permanent docs never quote the owner:** `docs/`, lore, the chronicle, READMEs, changelogs, code comments and the knowledge hub. They state the decision in neutral words.
- Why: a quote read as a standing instruction goes stale when the decision changes; a neutral statement with its date stays correct.

## How to write a permanent record

- State the decision, rule or rationale as a plain statement. Add the owner decision's date where the date is part of the record, as "(owner decision, YYYY-MM-DD)".
- Record a sign-off as "accepted by the owner on <date>", plus any plain-language qualifier the owner gave, for example "accepted without a device check; the owner took the agent's report".
- Keep nuance as plain statements, not as quotes.
- Keep commit hashes. Keep product UI text and rule text quoted, as product text: those are the game's words, not the owner's.

Before (permanent page): The owner said, "Make the save button bigger, it's too hard to hit." Accepted!

After (permanent page): Decision (owner decision, 2026-10-12): enlarge the save button so it is easy to hit on a phone. Accepted by the owner on 2026-10-14, checked on the desktop build only.

## Converting at close-out

1. Before a forge item's facts move to a permanent page, rewrite each owner quote as a neutral statement.
2. Delete the quotation marks and the quoted text in the same change.
3. Search the permanent pages for quotation marks after the move. Why: a quote left behind is found only by a later search.

## Recording in transient docs

- Quote the owner's words verbatim, with a reference to where they appear.
- Mark anything else as a paraphrase.
- Never upgrade wording. "Works", "fixed", "looks good" and "confirmed" are not "accepted". Record each as its own words.
- Keep a sub-question unconfirmed until the owner confirms it. Do not let it inherit its parent's acceptance.
- Keep a standing list with four parts: accepted, implemented and awaiting the owner's check, blocked on an answer, queued. Answer "what is pending?" from that list.

## Scope changes

- Route new owner input to the right place: an active topic if it matches one, otherwise the future-work list. Give it its own ID.
- A scope change needs the owner's explicit decision. Do not decide scope on the owner's behalf.
