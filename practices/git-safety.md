# Git safety

- **Scope:** How do I undo, reset or set aside work in a git repository without losing anything the owner or another agent wrote?
- **Keywords:** git, checkout, restore, reset, discard, stash, push -u, worktree, uncommitted work, safe revert, force push, amend, local commits, remote
- **Status:** current
- **Updated:** 2026-11-01
- **Sources:** distilled from a Godot project's git rules and lessons (ganvchi-court); see `recall/` for the scenarios

## Rules

- Never discard work with `git checkout -- <file>`, `git restore`, `git reset --hard` or `git clean`. Each one can erase uncommitted work, including your own experiment.
- To set work aside, use `git stash push -u -m <name>`. It keeps untracked files and gives the stash a name you can find.
- To undo your own experiment, patch the file back by hand, or stash it. Never rely on a checkout to undo it.
- Commit only when the owner asks, or when the project's rules say commits are routine. Keep one logical change per commit.
- Do not amend, rebase or force-push commits you did not make in this session.
- Push only when the owner says so. Never force-push. After a push, compare the local tip with the remote tip.
- Before removing a worktree, use `git worktree remove`, not a recursive delete.
- Before editing a file, check its line endings. A tool that rewrites them produces a whole-file diff that hides the real change.

## Why

A weaker agent reached for `git checkout` to undo its own experiment and erased the
only copy of a working change. A stash costs one command and loses nothing.
