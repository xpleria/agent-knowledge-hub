# Git rules for project work: commits, pushes and undo

- **Scope:** Which git actions may an agent take in a project without asking, and how are commits, pushes and undo kept safe?
- **Keywords:** git, commit, local commit, push, remote, force push, amend, stash, checkout, restore, reset, rename, git mv, uncommitted work, one writer, stop and ask, deploy, permission, tag
- **Status:** current
- **Updated:** 2026-11-07
- **Sources:** the owner's lifecycle prompt, sections 5 (Phases 0 and 3), merged into this hub 2026-11-07; this hub's `practices/git-safety.md` and `practices/one-writer-per-tree.md`

Rule first: no push and no remote unless the owner says so. Commit only when the owner or the project permits commits.

## Commits

- With permission, commit each logical change locally as it completes: one logical change per commit, grouped by concern, see [practices/commit-granularity.md](../practices/commit-granularity.md), with a message that names the folder it touches.
- Without permission, leave the changes uncommitted and say so in the report.
- When commits are permitted, commit before a deploy, so each item is visible on its own (see [50-deploy-and-verify-habits.md](50-deploy-and-verify-habits.md)).
- In a migration, commit pure renames (`git mv`) separately from content edits, so rename detection and `git log --follow` keep working.

## Pushing and rewriting history

- Never create or push a tag unless the owner says so. A release tag is the owner's act.
- Push only when the owner says so. Never force-push.
- Do not amend, rebase or force-push commits you did not make in this session.
- After a push, compare the local tip with the remote tip.

## Undo and set-aside

- Never discard work with `git checkout -- <file>`, `git restore`, `git reset --hard` or `git clean`.
- To set work aside, use `git stash push -u -m <name>` (details in [practices/git-safety.md](../practices/git-safety.md)).

## Other writers

- If someone else's uncommitted work is in the tree, or another agent is actively writing there, stop and ask before any migration or cleanup.
- For a deploy in the same situation, say so and let the owner choose.
- One writing agent per working tree at a time (see [practices/one-writer-per-tree.md](../practices/one-writer-per-tree.md)).

*Why:* a commit the owner did not expect is hard to unpick once it is shared, and a discard erases work that cannot be recovered.
