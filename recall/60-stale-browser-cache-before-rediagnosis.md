# Stale browser cache suspected before re-diagnosing

- **Scope:** When players still see an old build after a correct deploy, how do I tell a stale cache from a code fault?
- **Keywords:** browser cache, stale build, no-store, cache-control, served hash, deploy, revalidate, old pack
- **Status:** current
- **Updated:** 2026-11-01
- **Source project:** ganvchi-court

## What happened

After a deploy, a tester reported the old behaviour. The team began to re-diagnose the
code. The served file already matched the local build, and the browser was still running
an earlier copy it had cached.

## Lesson

- Before re-diagnosing a "still broken after deploy" report, compare the served main artefact's hash with the local build.
- If the hashes match, check the cache headers on the main entry and the artefact. They must say no-store, or the browser may revalidate and keep the old copy.
- Ask the tester to hard-reload or use a private window, and note whether the build identifier changed.
- Only after the hash matches and the cache is ruled out should you treat the report as a code fault.

## Why

Re-diagnosing a working build wastes a full cycle and can lead to a "fix" that changes
nothing the player sees.
