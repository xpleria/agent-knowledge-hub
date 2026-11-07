# Transitions

- **Scope:** Which document transition does each owner sign-off trigger, and what happens in the same session?
- **Keywords:** transitions, commencement, acceptance, partial acceptance, deferral, cancellation, weave, shed, forge topic deletion, horizon, lore, chronicle, same session, progress file
- **Status:** current
- **Updated:** 2026-11-07
- **Sources:** the owner's lifecycle prompt, sections 4.4 and 4.6; owner decisions of 2026-11-07 on transitions

Rule first: each transition follows its owner sign-off in the same session. No transition
happens without a sign-off (see [31-sign-off-rules.md](31-sign-off-rules.md)).

| Sign-off | Transition |
| --- | --- |
| Commencement | Create the forge topic folder with its index, or move the topic in from `03-horizon/` and delete the horizon item. Other forge files follow as needed (see [33-forge-topic-file-set.md](33-forge-topic-file-set.md)). |
| Acceptance | Weave: (1) verified facts about the result go to `docs/`; (2) lessons, rationale and pitfalls go to `01-lore/` (see [36-lore-rules.md](36-lore-rules.md)); (3) any deferred remainder goes to `03-horizon/`; (4) a thin chronicle entry is written; (5) process material (logs, step tracking, transient status, deploy records) is shed; (6) the forge topic folder is deleted. |
| Partial acceptance | Weave only the accepted part, as in acceptance. The rest stays in forge, or goes to horizon if the owner defers it. The chronicle entry names the accepted part. |
| Deferral | Move the topic to `03-horizon/` with its remaining state summarised, and move its lessons so far to lore. Paused work is not deferred (see [26-status-vocabulary.md](26-status-vocabulary.md)). |
| Cancellation | Move its lessons to lore, write a chronicle entry, and shed the rest. |

## Rules that apply to every transition

- Work on a forge topic updates its progress file in the same session.
- Never start a parallel topic for work an active topic already covers. Continue that topic.
- Write the chronicle entry before deleting the forge folder. After deletion, the entry is the
  register of the closed topic.
- A deferral writes no chronicle entry. The entry is written when the deferred work later
  closes. *(Interpretation of decision 2: a deferred topic is not closed.)*
- Shedding is safe because git history keeps the material. Deleted, not archived. When an old
  detail is needed, cite its commit SHA.

*Why:* a sign-off that moves nothing leaves finished work in forge, where it reads as still
active.
