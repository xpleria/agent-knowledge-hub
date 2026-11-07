# Verifying a claim before it enters docs

- **Scope:** What must a claim be checked against before it is written into `docs/`, and where does an unverified claim go?
- **Keywords:** verify, verification, to verify, unverified claim, not determinable, status line, git history, tests, owner ruling, forge, horizon, claim
- **Status:** current
- **Updated:** 2026-11-07
- **Sources:** the owner's lifecycle prompt, sections 1 and 5 (Phase 1), merged into this hub 2026-11-07; this hub's `practices/evidence-and-verification.md`

Rule first: a claim enters `docs/` only after it is verified against the current code, its tests, or an owner ruling.

## What counts as verified

- The current code, read at the cited path and symbol.
- Tests that exercise the behaviour in question and pass.
- An owner ruling, recorded with its date and a reference.

## What never counts

- A document's own status line. Status lines rot fastest. Verify the state against the code and the git history.
- A passing suite verifies behaviour. It does not accept work (see [31-sign-off-rules.md](31-sign-off-rules.md)).
- An agent's own judgement that work is done is a claim to verify, not a fact.

## A claim that cannot be verified

- Record it as "to verify", in the active forge topic doing the related work, or in `03-horizon/` when no topic does.
- Never create a forge topic just to hold it. A forge topic needs a commencement sign-off (see [33-forge-topic-file-set.md](33-forge-topic-file-set.md)).
- Do not write "not determinable" into `docs/`. Record the claim as "to verify" instead.

## When a "to verify" claim is verified

- Move it into `docs/` in the same change, and delete its "to verify" entry.

*Why:* a claim written as fact is trusted by every later reader. A "to verify" entry keeps the gap visible until someone closes it.
