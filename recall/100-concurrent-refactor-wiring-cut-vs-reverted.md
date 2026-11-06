# Concurrent refactor: wiring cut versus work reverted

- **Scope:** When code disappears after another agent's uncommitted refactor, is the work lost, or only cut off from its callers?
- **Keywords:** wiring cut, work reverted, concurrent refactor, restore, HEAD, parse error, call sites, methods removed, mechanical restore, parsed body
- **Status:** current
- **Source project:** ganvchi-court

## What happened

Another agent's uncommitted refactor removed many methods from a file but kept their call
sites. The file no longer parsed and several tests failed. The first diagnosis was that the
work was gone. The constants and helpers were still present; only the method that tied
them together had been cut.

## Lesson

- Diagnose a wiring cut against a reverted change before restoring anything. Compare the
  file with the last commit, function by function.
- Restore from committed history verbatim, then re-apply later changes on top.
- Verify a mechanical restore by comparing each function body with the source. A truncated
  function still parses, so "the file parses" is not enough.
- Do not overwrite another agent's uncommitted work to fix it. Stash it first.

## Why

Restoring blindly can erase the other agent's newer changes; leaving the cut in place
keeps the tests red.
