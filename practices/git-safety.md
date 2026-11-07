# Git safety

- **Scope:** How do I undo, reset or set aside work in a git repository without losing anything the owner or another agent wrote?
- **Keywords:** git, checkout, restore, reset, discard, stash, push -u, worktree, uncommitted work, safe revert, force push, amend, local commits, remote
- **Status:** current
- **Updated:** 2026-11-07
- **Sources:** distilled from a Godot project's git rules and lessons; see `recall/` for the scenarios

## Rules

- Never discard work with `git checkout -- <file>`, `git restore`, `git reset --hard` or `git clean`. Each one can erase uncommitted work, including your own experiment.
- To set work aside, use `git stash push -u -m <name>`. It keeps untracked files and gives the stash a name you can find.
- To undo your own experiment, patch the file back by hand, or stash it. Never rely on a checkout to undo it.
- Commit each logical change locally as it completes, one logical change per commit, but only when the owner or the project permits commits. Otherwise leave the changes uncommitted and say so (see [project-setup/45-git-rules.md](../project-setup/45-git-rules.md)).
- Do not amend, rebase or force-push commits you did not make in this session.
- Push only when the owner says so. Never force-push. After a push, compare the local tip with the remote tip.
- Before removing a worktree, use `git worktree remove`, not a recursive delete.
- Before editing a file, check its line endings. A tool that rewrites them produces a whole-file diff that hides the real change.

## Why

A weaker agent reached for `git checkout` to undo its own experiment and erased the
only copy of a working change. A stash costs one command and loses nothing.

## Stash, step by step

- `git stash push -u -m <name>` sets work aside, including untracked files.
- `git stash list` finds it again by its name.
- `git stash apply` restores it. Check the result before you drop anything.
- `git stash drop` removes the stash only after the restored work is checked.

## Related

- [one-writer-per-tree.md](one-writer-per-tree.md): one writing agent per tree, and what to do after a collision.
- [project-setup/45-git-rules.md](../project-setup/45-git-rules.md): commit, push and permission rules for projects.
- `recall/30-two-writers-one-tree-tangled-commits.md`: the scenario behind the one-writer rule.

