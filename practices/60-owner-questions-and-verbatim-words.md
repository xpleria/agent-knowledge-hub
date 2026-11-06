# Owner questions and verbatim words

- **Scope:** How should an agent put a question to the owner, and how does it record what the owner said without rewording it?
- **Keywords:** owner question, decision, options, recommendation, verbatim, quote, paraphrase, accepted, confirmed, works, fixed, standing list, pending, stale premise, scope change
- **Status:** current
- **Sources:** distilled from a Godot project's owner-communication rules (ganvchi-court)

## Asking

- Put each question as: the decision, the context, the options with their impact on the project, then a recommended option first.
- Batch independent questions into one message.
- Do not ask what the plan already recommends, unless the choice really is open.
- If the premise is stale, because the code or an earlier acceptance has already superseded it, say so and propose closing the question instead of asking it.
- For wording decisions, read the current strings first, then propose two or three candidates with a recommendation.
- Ask before mapping a key or button to a consequential action.

## Recording

- Quote the owner's words verbatim, in quotation marks, with a reference to where they appear.
- Mark anything else as a paraphrase.
- Never upgrade wording. "Works", "fixed", "looks good" and "confirmed" are not "accepted". Record each as its own words.
- Keep a sub-question unconfirmed until the owner confirms it. Do not let it inherit its parent's acceptance.
- Keep a standing list with four parts: accepted, implemented and awaiting the owner's check, blocked on an answer, queued. Answer "what is pending?" from that list.

## Scope changes

- Route new owner input to the right place: an active topic if it matches one, otherwise the future-work list. Give it its own ID.
- A scope change needs the owner's explicit decision. Do not decide scope on the owner's behalf.
