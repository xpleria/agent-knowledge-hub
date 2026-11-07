# Migration verification checklist

- **Scope:** Which checks must pass, and which results must be reported, before a migration counts as done?
- **Keywords:** verify, checklist, names, numbering, indexes, headers, sign-off field, links, stale references, status words, grep, sidecars, thresholds, build, test, agent section, git status, Phase 4
- **Status:** current
- **Updated:** 2026-11-07
- **Sources:** the owner's lifecycle prompt, section 5 (Phase 4), merged into this hub 2026-11-07; [22-split-and-merge-thresholds.md](22-split-and-merge-thresholds.md); [15-uppercase-and-root-files.md](15-uppercase-and-root-files.md)

Rule first: run every check, fix every failure, and only then report. Report the real command output, not a description of it.

- [ ] Every name is lowercase-hyphen and carries a topic slug. No name is a bare role word, and none has a version, status or date suffix. The only uppercase names are the exceptions in [15-uppercase-and-root-files.md](15-uppercase-and-root-files.md).
- [ ] Every directory's entries have unique two-digit prefixes in reading order, with `00` for the index and `99` for evidence only. Names minus their numbers are unique within each tree. Permanent IDs are unchanged.
- [ ] Every subfolder has a `00-<slug>-index.md` that lists exactly its children, and every tree root has a `README.md`.
- [ ] Every Markdown page, except the root entry files, has the header block (see [25-header-fields.md](25-header-fields.md)). Every forge topic index has a `Sign-off` field.
- [ ] Every relative link in both trees resolves. No reference anywhere in the repository still points at an old path or name: code comments, tests, tooling and CI included.
- [ ] `docs/` holds no status, plan, progress, proposal or open-question language. Grep `docs/` for: pending, todo, not yet, in progress, planned, proposed, open question, blocked, next step. Classify each hit as a legitimate normative or descriptive use, or as a violation to fix.
- [ ] No runnable code, generated sidecars or caches remain in either tree.
- [ ] The size triggers hold (see [22-split-and-merge-thresholds.md](22-split-and-merge-thresholds.md)): no file over about 300 lines without a recorded reason, no folder over about 12 entries, and no folder with a single content child.
- [ ] If any code, test, tooling or CI file changed, even only in comments, the project's build and test suite still pass.
- [ ] The agent-instruction section exists once. Its placeholders are filled, every path in it resolves, verbatim copies are identical, and no other passage in the agent files describes the old layout.
- [ ] `git status` shows only the intended paths.

## How to run the checks

- Use the project's own tools where they exist. A check that could not be run is reported as not run, never as passed.
- Status words: `grep -rniE "pending|todo|not yet|in progress|planned|proposed|open question|blocked|next step" docs/`, then classify every hit.
- Links: test each relative link target with the file system, not by eye.
- Sizes: `wc -l` on each page in the trees.

Report each command and its output in the final report (see [66-migration-report-and-obligations.md](66-migration-report-and-obligations.md)).
