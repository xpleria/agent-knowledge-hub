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
- Say what was verified and at which level (see [evidence-levels.md](evidence-levels.md)). Name what was not verified.
- Quote the test output's failing names. A count alone does not explain a failure.
- A non-reproduction is a valid finding. Report it with the steps you ran; do not invent a fix.
- A crash is not a pass. A run that dies without its summary line, or a check that passes when a result is missing, turns a crash green. Treat the absence of the run's summary as a failure.
- Record the commit and the clean-tree state with every suite result. A count taken from a dirty, mid-change tree cannot be reproduced.
- Do not freeze test counts in docs. Counts change with each change; put the run summary in the commit message or review note.
- Audit source to test: pair each changed source file with the test that pins it. State the verification boundary: what the suite does not reach.
- Write "not reproduced" when a defect does not reproduce on the steps given. Never write "fixed" or "cannot happen" for an unreproduced defect.

## Why

A delegated agent once reported earlier work as landed without reading the output that
would show it. The owner then trusted a state that did not exist. Evidence is cheap;
an unverified "done" is expensive. See `recall/10-subagent-claimed-landed-without-evidence.md`.

## Reporting format

- A table: claim, commit or evidence, level reached, not verified.
- Evidence levels (headless suite, served artefact, shipped behaviour, browser flow interaction, device review) name how far a check reached, and what each one does not prove. See [evidence-levels.md](evidence-levels.md). They are not evidence files (see [project-setup/37-evidence-and-helpers.md](../project-setup/37-evidence-and-helpers.md)).
- Keep "implemented", "tested", "deployed" and "accepted" as separate words. Only the owner's acceptance gives "accepted".
