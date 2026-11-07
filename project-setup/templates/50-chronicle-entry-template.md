# Chronicle entry: <Topic title>

- **Scope:** Which forge topic closed, when, and where did its facts, lessons and deferred items go?
- **Keywords:** <topic slug>, closed, acceptance, sign-off, commit range, facts moved, lessons moved, deferred
- **Status:** chronicle
- **Updated:** <YYYY-MM-DD of the last change to this entry>
- **Sources:** the topic's index as it stood at close; the commit range below
- **Sign-off:** <accepted | partly accepted | cancelled> by the owner on <YYYY-MM-DD>; reference: <message id, link, commit or PR>; <neutral qualifier, or none>

## Closed

- <YYYY-MM-DD>: closed by owner acceptance of <the whole topic, or the named part only>, or by owner cancellation.

## What shipped (optional)

- <Two to four plain lines for a developer: what the change now does. Omit the section if it adds nothing.>

## Facts went to

- <docs page, relative link>: <one line: what the page now states>
- <none, if the topic changed no settled fact>

## Lessons went to

- <lore page, relative link>: <one line: the subject it was woven into>
- <none, if the topic produced no lesson>

## Deferred

- <item> → [horizon <NN>](<relative link to the horizon page>)
- <none, if nothing was deferred>

## Commits

- <first-hash>..<last-hash>

## Notes

- Write this entry once, after sign-off and before the forge folder is deleted.
- Shed everything else: git history keeps the commits, rounds and drafts. Cite a commit SHA when an old detail is needed.
- No commit lists, no round logs, no narrative. "What shipped" stays a few lines. Facts belong in docs and lessons in lore.
- Keep the dates. Correct this entry only by adding a dated note at the end; never rewrite the text above.
- Never quote the owner here. Give the sign-off reference as a message id, link, commit or PR.
- Record no tokens, passwords, host names, user names or account identifiers.
