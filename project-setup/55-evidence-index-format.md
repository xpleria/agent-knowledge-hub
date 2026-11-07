# Evidence index format

- **Scope:** What columns does an evidence index carry, and what does each row record?
- **Keywords:** evidence index, 00 evidence index, columns, file, what it shows, cited by, how produced, command, commit, tool path, one row per file, sign-off none
- **Status:** current
- **Updated:** 2026-11-07
- **Sources:** the owner's lifecycle prompt, section 2.6 (evidence index); see [37-evidence-and-helpers.md](37-evidence-and-helpers.md)

Rule first: `00-<topic-slug>-evidence-index.md` has one table row per evidence file, with the
four columns below.

| Column | Holds |
| --- | --- |
| File | A relative link to the evidence file. |
| What it shows | One line: the measurement or fact the file shows. |
| Cited by | The statement (page and heading) that cites this file. |
| How produced | The command run, and the commit or tool path it ran from. |

## Rules

- A row whose file no live statement cites is removed, and the file is deleted with it.
- A helper cited in this index is named by its path and the command that runs it. The helper
  lives in the tooling folder, not in the evidence folder.
- If the command depends on a helper that was deleted, record the last commit where the helper existed.
- The evidence index is an agent-docs index. Its `Sign-off` field is `none`, because no transition
  creates it (see [31-sign-off-rules.md](31-sign-off-rules.md)).

*Why:* a reader who doubts a statement needs the file, the claim it supports, and a way to
reproduce the file. Missing any one of the three makes the evidence unusable.
