# Migration report and standing obligations after migration

- **Scope:** What does the final migration report contain, and which obligations hold for the project after the migration?
- **Keywords:** report, final report, case, tree, moved, woven, promoted, shed, relocated, transitions, sign-off references, verification output, unresolved, unverified, standing obligations, progress file, conformant
- **Status:** current
- **Updated:** 2026-11-07
- **Sources:** the owner's lifecycle prompt, sections 5 (Phase 5) and 7.3, merged into this hub 2026-11-07; [60-migrate-existing-project.md](60-migrate-existing-project.md)

Rule first: the report separates verified work from unverified work, and it shows real command output.

## Phase 5: the report

The report states:

- the case, A to D (see [60-migrate-existing-project.md](60-migrate-existing-project.md));
- the final tree at topic level;
- what was moved, woven, promoted to `docs/`, shed or relocated;
- each transition performed, with its sign-off reference (see [31-sign-off-rules.md](31-sign-off-rules.md));
- the verification results, with the actual command output;
- anything left unresolved;
- unverified work, kept clearly apart from verified work.

## Standing obligations after the migration

- Every change that alters behaviour updates the matching `docs/` fact in the same change, or waits in the progress file while it sits inside an open forge topic (see [30-lifecycle-and-acceptance.md](30-lifecycle-and-acceptance.md)).
- Every work session updates the progress file of its forge topic.
- Every owner sign-off triggers its transition in the same session (see [32-transitions.md](32-transitions.md)).
- The trees stay conformant with [18-conventions-location.md](18-conventions-location.md). A violation found is fixed in place.
