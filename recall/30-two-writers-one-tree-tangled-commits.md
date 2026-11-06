# Two writers in one tree tangled commits

- **Scope:** What went wrong when two agents edited one working tree at the same time, and how is it prevented?
- **Keywords:** two writers, one writer per tree, concurrent edits, tangled commits, collision, CRLF, line endings, queue
- **Status:** current
- **Updated:** 2026-11-01
- **Source project:** ganvchi-court

## What happened

Two implementers worked in the same tree at once. Their edits to shared files collided,
line endings were rewritten by one of them, and the commits mixed both changes. The owner
could not tell which change belonged to which item.

## Lesson

- Run one writing agent per working tree. Queue the next writer until the first has finished and committed.
- Read-only agents may run alongside a writer, but they change nothing.
- Give parallel writers disjoint files, named before they start.
- When an owner adds feedback mid-run, steer the running agent instead of starting a second writer.

## Why

A commit that mixes two items cannot be reviewed or reverted cleanly, and it hides which
change caused a regression.
