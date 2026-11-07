# Headers and status

- **Scope:** Which fields does every page's header carry, and which values may its Status take?
- **Keywords:** header, title, Scope, Keywords, Status, Updated, Sources, Sign-off, status vocabulary, current, lore, forge active paused blocked, horizon deferred idea, chronicle, paused, awaiting owner check, stage label, progress file
- **Status:** current
- **Updated:** 2026-11-07
- **Sources:** the owner's lifecycle prompt, sections 2.4 (file header) and 4.2 (paused work); the hub's `project-setup/30-lifecycle-and-acceptance.md` for the progress file rule

Rule first: every Markdown page in a project opens with a title that names its topic, then
the header block below. Agent instruction files (`AGENTS.md`, `CLAUDE.md`) are exempt
because agents load them in their own format.

```text
# <Title that names the topic>

- **Scope:** <one sentence: the single question this page answers>
- **Keywords:** <synonyms, identifiers and symbols a searcher would type>
- **Status:** <stage label, from the vocabulary below>
- **Updated:** <YYYY-MM-DD of the last substantive change>
- **Sources:** <authoritative docs and code the page derives from>
- **Sign-off:** <agent-docs indexes only; see the lifecycle page>
```

## Field rules

- **Title:** names the topic. Repeat the disambiguating noun, so "Card-sizing constants" and
  not "Constants".
- **Scope:** one sentence and one question. A page that needs two sentences is probably two
  pages (see [27-one-question-and-citations.md](27-one-question-and-citations.md)).
- **Updated:** the date of the last substantive change, not of any edit. A typo fix does not
  move it.
- **Sources:** the docs, code and tests the page is checked against. Cite code by path and
  symbol (see [27-one-question-and-citations.md](27-one-question-and-citations.md)).
- **Sign-off:** present on agent-docs indexes only. Omit it everywhere else.

*Why:* the header lets a retrieved chunk say what it is, how current it is, and what it rests on.

## Status vocabulary

| Stage | Values |
| --- | --- |
| Docs | `current` |
| Lore | `lore` |
| Forge | `forge: active`, `forge: paused`, `forge: blocked` |
| Horizon | `horizon: deferred`, `horizon: idea` |
| Chronicle | `chronicle` |

- Paused is not deferred. Paused work stays in forge, with `forge: paused` and a reason in its
  progress file. Deferred work moves to horizon.
- `implemented + deployed, awaiting owner check` is not a Status value. It is an entry in the
  standing list of the progress file.
- The header Status is the stage label. The actual status content lives only in the progress
  file. An index carries a one-line summary and a link to that file.

*Why:* a closed value set lets a search filter by stage. Status content in two places drifts
apart.

## Hub pages

- In a hub page, Sources may name an origin project only generically, for example "a Godot
  project", never by its name.
