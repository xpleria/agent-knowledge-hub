# Sign-off rules

- **Scope:** Who signs off work, what counts as a sign-off, and which records must carry one?
- **Keywords:** sign-off, owner sign-off, commence, accept, defer, cancel, reference, date, quote, migration proposal, unsure, infer, transition, register entry, chronicle, forge index, horizon item, lore index
- **Status:** current
- **Updated:** 2026-11-07
- **Sources:** the owner's lifecycle prompt, section 4.5 (sign-off rules); owner decisions of 2026-11-07 on sign-off placement

Rule first: the owner signs off work, never a document move. A sign-off commences, accepts,
defers or cancels a piece of work. The document transition follows from it without a second
approval (see [32-transitions.md](32-transitions.md)).

## What counts as a sign-off

- Only an explicit owner statement that commences, accepts, defers or cancels work counts.
- Passing tests, a clean review, a successful deploy and an agent's own judgement that work is
  done are not sign-off.
- An owner's approval of the listed rows of a migration proposal counts as the sign-off for
  those transitions.
- If you are unsure whether a statement was a sign-off, ask the owner. Never infer it.

*Why:* a document moves only when the owner has decided the work moves. Agent judgement that
work is finished is a claim to verify, not a decision.

## Where the sign-off is recorded

| Record | Sign-off field |
| --- | --- |
| Forge topic index | Required: the sign-off that authorised the work. |
| Horizon item | `none` until a deferral creates the item; then the deferral sign-off. |
| Lore topic index, or a lore page a transition created | `none` unless a transition created it; then the sign-off that created it. |
| Stage index (for example `01-lore/00-lore-index.md`) | `none`: no transition created it. |
| Chronicle entry | Required: the closing sign-off. |

## Form of the field

- Form: `<commenced | accepted | partly accepted | deferred | cancelled> by the owner on
  YYYY-MM-DD; reference: <message id, link, commit or PR>; <qualifier, or none>`.
- The reference is a message id, a link, a commit or a PR.
- A pre-existing sign-off with no traceable reference is written `reference: not recorded`.
  Never invent a reference.
- A short owner quote may serve as the reference only in transient pages: forge, horizon and
  briefs. Chronicle entries, lore and docs record the date and a non-quote reference.
- The qualifier is the owner's plain-language qualification, written as a neutral statement.

*Why:* the date and a fixed reference let a later reader check the record. A quote in a
permanent page reads as a standing instruction after the decision changes.

## After a sign-off

- The transition happens in the same session as the sign-off.
- On acceptance, the receiving records are the chronicle entry plus the docs and lore changes.
