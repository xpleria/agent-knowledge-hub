# Forge topic file set

- **Scope:** Which files does a forge topic folder hold, which are required, and when is each one created?
- **Keywords:** forge topic, file set, index, playbook, plan, progress, decisions, open questions, findings, defects, log, evidence, commencement, claim, unverified, 00, 10, 20, 30, 40, 99
- **Status:** current
- **Updated:** 2026-11-07
- **Sources:** the owner's lifecycle prompt, section 4.2 (file set table); owner decisions of 2026-11-07 on the forge file set

Rule first: a forge topic is one folder, `02-forge/NN-<topic-slug>/`. Its files are created as
their content arrives, not all at commencement.

| File | Created | Answers |
| --- | --- | --- |
| `00-<slug>-index.md` | At commencement | Goal, scope, Sign-off, one-line status, reading guide, map. |
| `10-<slug>-playbook.md` | When the work has its own method | How the workstream is done: conventions, commands, gates, how to verify. |
| `20-<slug>-plan.md` | Once the work is staged | The stages. Each stage ends in observable acceptance checks. |
| `30-<slug>-progress.md` | Once any work has happened | The single source of status: verified done, built but unverified, broken, blockers, next actions. |
| `40-<slug>-<kind>.md` | As needed | One kind per file. Any kind named for the question it answers, for example `decisions`, `open-questions`, `findings`, `defects`, `log`, `inventory` or `context`. |
| `99-<slug>-evidence/` | As needed | Evidence that a live statement cites (see [37-evidence-and-helpers.md](37-evidence-and-helpers.md)). |

## Rules

- The index is the only file required at commencement. It carries the authorising sign-off
  (see [31-sign-off-rules.md](31-sign-off-rules.md)).
- Status lives only in the progress file. The index carries a one-line summary and a link to it.
- A forge topic is never created just to hold an unverified claim. Record the claim as "to
  verify" in the active topic that does related work, or in horizon.
- Each `40+` file holds one kind of statement. Split a file that mixes kinds.
- The `40+` kinds are open. Keep the topic slug in every name (`40-<slug>-findings.md`).
- The progress file holds no log. A decision log goes to `40-<slug>-decisions.md`.
- Any entry may be promoted to a folder under the split rules in
  [22-split-and-merge-thresholds.md](22-split-and-merge-thresholds.md).

*Why:* empty files read as work that has happened, and a claim without a home in an active topic gets lost.
