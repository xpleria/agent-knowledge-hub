# Recall index

- **Scope:** How does an agent find a past scenario or lesson in the recall journal when the owner asks for it?
- **Keywords:** recall, remember, search, grep, journal, scenario, lesson, index, keywords, source project
- **Status:** current
- **Updated:** 2026-11-01
- **Sources:** the entries listed below; `contribute.md` (*Add a recall entry*)

## How to search

Search the keywords with grep. Use several words and try synonyms. Examples:

```bash
grep -ril "overclaim" recall/
grep -ri -n "stash\|checkout" recall/
grep -rl "Source project: ganvchi-court" recall/
```

1. Start with the owner's words. Grep each distinctive word, case-insensitively.
2. Open the matching files. Check the Scope line first; it says whether the entry fits.
3. Read the lesson section. Note the source project, and check the lesson applies to yours.
4. If nothing matches, say so. Do not invent a recollection.

## Entries

| Entry | Scope question | Keywords |
| --- | --- | --- |
| [10-subagent-claimed-landed-without-evidence.md](10-subagent-claimed-landed-without-evidence.md) | A delegated report said "landed" without evidence: how do I check? | overclaim, landed, self-report, continuation |
| [20-auto-denied-recursive-delete-stopped-run.md](20-auto-denied-recursive-delete-stopped-run.md) | A recursive delete stopped a delegated run: what to do instead? | rm -rf, denied, approval, recursive delete |
| [30-two-writers-one-tree-tangled-commits.md](30-two-writers-one-tree-tangled-commits.md) | Two writers in one tree mixed their commits: how to prevent it? | one writer, collision, commits, worktree |
| [40-touch-emulation-sends-four-events.md](40-touch-emulation-sends-four-events.md) | A tap closed a dialog and the control behind reacted: why? | touch, emulated mouse, pointer, dialog, scrim |
| [50-relayout-must-equal-fresh-build.md](50-relayout-must-equal-fresh-build.md) | A resized view differs from a freshly built one: how do I test it? | relayout, fresh layout, rotation, minimum height |
| [60-stale-browser-cache-before-rediagnosis.md](60-stale-browser-cache-before-rediagnosis.md) | Players still see the old build after a deploy: cache or code? | cache, no-store, served hash, deploy |
| [70-protected-file-edited-by-orchestrator.md](70-protected-file-edited-by-orchestrator.md) | Who edits a protected instruction file? | protected file, AGENTS.md, approval, orchestrator |
| [80-transient-ftp-451-retry.md](80-transient-ftp-451-retry.md) | An upload failed with a transient 451: retry or switch method? | FTP, 451, retry, upload, served hash |
| [90-flaky-test-failure-must-be-named.md](90-flaky-test-failure-must-be-named.md) | A test failed once and passed later: how is that reported? | flaky, failing test, name, full suite |
| [100-concurrent-refactor-wiring-cut-vs-reverted.md](100-concurrent-refactor-wiring-cut-vs-reverted.md) | Code vanished after a concurrent refactor: lost or cut off? | wiring cut, reverted, restore, HEAD, parse |
| [110-headless-window-false-red.md](110-headless-window-false-red.md) | A UI test is red but the product works: harness or product? | headless, false red, viewport, window size |
| [120-container-min-size-shifts-siblings.md](120-container-min-size-shifts-siblings.md) | Adding an icon moved its neighbours: why? | container, minimum size, icon, sibling shift |

## Adding entries

Follow `contribute.md`. Use the next free number in steps of 10, and add one row here.
