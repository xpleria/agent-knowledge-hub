# Forge progress: <Topic name>

- **Scope:** What is the current state of this workstream, and what are the next actions?
- **Keywords:** <topic slug>, progress, status, verified, built but unverified, broken, blockers, next actions, standing list, pending docs, awaiting owner check, blocked, queued
- **Status:** <forge: active | paused | blocked>
- **Updated:** <YYYY-MM-DD>
- **Sources:** <playbook, plan and evidence files in this folder; the code, tests and docs they cite>

This file is the single source of status for the topic. The index links here and gives only a
one-line summary.

## Verified done

- <Item, the level it was verified at, and its commit.>
- <none yet>

## Built but unverified

- <Item, and the check that is still missing.>
- <none yet>

## Broken

- <Item, and what fails.>
- <none yet>

## Blockers

- <Blocker, and the owner answer or file it waits for.>
- <none yet>

## Standing list

- **Accepted (owner's words):** <none yet>
- **Implemented, awaiting owner check:** <none yet; for example "implemented + deployed, awaiting owner check">
- **Blocked on an owner answer:** <none yet>
- **Queued:** <none yet>

## Pending docs update

<List the settled-facts doc changes that wait for acceptance. Write "none" if none.>

## Next actions

1. <Next concrete step, with the file or test it touches.>
2. <Following step.>

## Notes

- Quote owner words verbatim here: a forge file is transient. At close-out, convert each quote to a neutral statement before the chronicle entry is written. Do not turn "works" or "fixed" into "accepted".
- This file holds no log. A decision log goes to `40-<slug>-decisions.md`.
- Put the reason behind the status here (the blocker, the pause). The index and the Status field never carry it.
- Keep this file to current state. Git keeps the history.
