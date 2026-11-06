# One writer per working tree

- **Scope:** How do several agents share one repository without tangling each other's edits, commits or deploys?
- **Keywords:** one writer, working tree, parallel agents, concurrent edit, file ownership, disjoint files, collision, read-only inspection, observer, in flight, CRLF, LF, line endings
- **Status:** current
- **Updated:** 2026-11-01
- **Sources:** distilled from a Godot project's multi-agent collaboration lessons (ganvchi-court)

## Rules

- Run one writing agent per working tree at a time. Queue the rest.
- Read-only agents may run alongside a writer: they inspect, grep and draft notes, and they change nothing.
- Give each parallel writer disjoint file ownership. Name the files before it starts.
- Treat a file that another agent is writing right now as in flight. A half-written function is a timing artefact; re-read before you report it.
- Do not run tests in a tree that another agent is actively writing, unless the owner asks.
- Keep reviewers' notes and implementers' plans in separate files. Reviewers append; they do not edit the implementer's files.

## When a collision happens

- Diagnose before you restore. A removed function whose call sites remain looks like lost work, but usually the work is only cut off from its callers.
- Restore from committed history verbatim, then re-apply later changes on top.
- Check a mechanical restore by comparing each function body with the source, not by checking that the file parses. A truncated function can parse.
- If you find another agent's uncommitted notes, keep them as found and surface any finding that exists only in them.

## Why

Two writers in one tree produced commits that mixed their work, and the owner could not
tell which change was which. See `recall/30-two-writers-one-tree-tangled-commits.md`.
