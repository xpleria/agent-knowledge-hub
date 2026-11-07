# Evidence and verification

- **Scope:** What evidence must back a claim that work is done, and how should a report word what was and was not verified?
- **Keywords:** evidence, verification, claim, self-report, landed, done, git log, git status, diff, hash, test output, not verified, non-reproduction, report wording
- **Status:** current
- **Updated:** 2026-11-07
- **Sources:** distilled from a Godot project's verification and orchestration lessons

## Rules

- Treat every delegated report as a self-report until you check it.
- Verify any claim that gates the next step with evidence: the commit in `git log`, the file in `git diff`, a hash comparison, or the test output file.
- Use the word "landed" only when the commit or the file is in the repository. Otherwise say "reported".
- Say what was verified and at which level. Name what was not verified.
- Quote the test output's failing names. A count alone does not explain a failure.
- A non-reproduction is a valid finding. Report it with the steps you ran; do not invent a fix.

## Why

A delegated agent once reported earlier work as landed without reading the output that
would show it. The owner then trusted a state that did not exist. Evidence is cheap;
an unverified "done" is expensive. See `recall/10-subagent-claimed-landed-without-evidence.md`.

## Reporting format

- A table: claim, commit or evidence, level reached, not verified.
- "Evidence levels" (served bytes, shipped behaviour, browser render, device) name how far a check reached. They are not evidence files (see [project-setup/37-evidence-and-helpers.md](../project-setup/37-evidence-and-helpers.md)).
- Keep "implemented", "tested", "deployed" and "accepted" as separate words. Only the owner's acceptance gives "accepted".
