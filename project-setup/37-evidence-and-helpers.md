# Evidence and helpers

- **Scope:** Where does evidence live, which evidence is kept, and where do helper programs go?
- **Keywords:** evidence, evidence files, 99 evidence folder, screenshots, text measurements, probe output, helper, probe, tooling folder, tools, throwaway, sidecar, cache, gitignore, exclusion, evidence levels, verification level
- **Status:** current
- **Updated:** 2026-11-07
- **Sources:** the owner's lifecycle prompt, section 2.6 (evidence and helper files); owner decisions of 2026-11-07 on evidence and helpers

Rule first: evidence lives in the topic it supports, in a `99-<topic-slug>-evidence/` folder.
No runnable code lives in either tree.

## Evidence

- Evidence is measurements, captures, probe output, screenshots and logs.
- Its files are lowercase, hyphen-separated and descriptively named. They carry no number,
  because they are cited, not read in sequence (see [21-numbering-rules.md](21-numbering-rules.md)).
- The folder holds `00-<topic-slug>-evidence-index.md`, which has one row per file (columns in
  [55-evidence-index-format.md](55-evidence-index-format.md)).
- Keep only evidence that a live statement cites. When the statement is shed, its evidence goes too.
- Prefer text measurements to screenshots. Use an image only when the picture is the claim, and
  give it a text description beside it.

*Why:* evidence no statement cites is a second copy of nothing, and it is read as proof of
something that no page claims.

## Helpers

- No runnable code in `docs/` or `agent-docs/`.
- A helper worth keeping (a probe, a measurement script, a generator) moves to the project's
  tooling folder, such as `tools/`. It follows that folder's conventions and is cited from the
  evidence index by path and command.
- A throwaway helper is deleted once its output is captured. If reproducing the result may
  matter, the evidence index records the exact command and the last commit where the helper existed.
- Generated sidecars and caches never enter the trees: engine import files, UID files,
  `__pycache__`, thumbnails. Exclude them with the tool's own mechanism (for example a
  `.gdignore` for Godot) and ignore them in version control.

## Two meanings of "evidence"

- "Evidence levels" in [50-deploy-and-verify-habits.md](50-deploy-and-verify-habits.md) and in
  [practices/evidence-levels.md](../practices/evidence-levels.md) are how far a check reached: served artefact, shipped behaviour,
  browser flow interaction, device review, and headless suite. They are a different concept from evidence files, which are the
  artefacts a statement cites.
