# Commit granularity

- **Scope:** How much work belongs in one commit, so that each commit is reviewable and no commit is broken on its own?
- **Keywords:** commit, granularity, one idea, split, merge, fixup, squash, rename, git mv, index row, links, message, folder, concern, delegated run, pushed history, rewrite
- **Status:** current
- **Updated:** 2026-11-07
- **Sources:** the owner's request for a balance between fragmented and oversized commits; this hub's `practices/git-safety.md` and `project-setup/45-git-rules.md`

## Rules

- One reviewable idea per commit. All edits that implement the same decision go together, even across files. A commit can be described in one sentence without "and".
- Size check: about 1 to 15 files, with a diff a reviewer can read in 10 to 15 minutes. Split a commit that is hard to review. Merge commits when one change needs several commits to be understood.
- Never split what breaks when separated: a page with its index row, a rule with the template that depends on it. No commit may leave a broken link or a stale index.
- A rename commit holds the `git mv` plus only the link repoints that the rename itself breaks. Content edits to the renamed file go in separate commits. Similarity stays high, so git still detects the rename and `git log --follow` keeps the history.
- Fold fixups (a typo, a missed link of the same change) into the commit they belong to, before pushing. Never add them as follow-up commits.
- Name the folder and the concern in the message, for example `project-setup: horizon group folders, no stubs`.
- A delegated run's brief says "group edits by concern, not by file". A run of one concern is about 1 to 5 commits.
- Do not rewrite pushed history to regroup commits. Regrouping is for unpushed commits only.

## Why

A commit that mixes two decisions cannot be reviewed or reverted on its own. A commit
split by file leaves a page without its index or a link without its target, and the
next reader finds a broken hub. Grouping by concern keeps each commit whole and
readable.

## Checking a commit before it is made

- `git diff --cached --stat` shows the file count. Above about 15 files, or a diff that
  needs more than 15 minutes, ask whether it is one idea.
- Read the one-sentence description aloud. If it needs "and", split it.
- Check the links and the index row in the same commit as the page they point to.

## Related

- [git-safety.md](git-safety.md): undo and set-aside rules, and when commits are allowed.
- [delegation-briefs.md](delegation-briefs.md): the brief line that asks for grouping by concern.
- [project-setup/45-git-rules.md](../project-setup/45-git-rules.md): commit and push permissions for projects.
