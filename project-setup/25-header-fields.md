# Header fields

- **Scope:** Which fields does every page's header carry, and what form does each field take?
- **Keywords:** header, title, Scope, Keywords, Status, Updated, Sources, Sign-off, header block, field rules, stage label, date, YYYY-MM-DD, agent files exempt
- **Status:** current
- **Updated:** 2026-11-07
- **Sources:** the owner's lifecycle prompt, section 2.4 (file header); the hub's `project-setup/26-status-vocabulary.md` for the Status values

Rule first: every Markdown page in a project opens with a title that names its topic, then
the header block below. Agent instruction files (`AGENTS.md`, `CLAUDE.md`) are exempt
because agents load them in their own format.

```text
# <Title that names the topic>

- **Scope:** <one sentence: the single question this page answers>
- **Keywords:** <synonyms, identifiers and symbols a searcher would type>
- **Status:** <stage label, from the vocabulary in [26-status-vocabulary.md](26-status-vocabulary.md)>
- **Updated:** <YYYY-MM-DD of the last substantive change>
- **Sources:** <authoritative docs and code the page derives from>
- **Sign-off:** <agent-docs indexes, horizon items and register entries only; see [31-sign-off-rules.md](31-sign-off-rules.md)>
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
- **Sign-off:** present on agent-docs indexes, horizon items and register entries (chronicle entries). Omit it everywhere else. Values and their form: see [31-sign-off-rules.md](31-sign-off-rules.md).

*Why:* the header lets a retrieved chunk say what it is, how current it is, and what it rests on.

## Hub pages

- In a hub page, Sources may name an origin project only generically, for example "a Godot
  project", never by its name.
