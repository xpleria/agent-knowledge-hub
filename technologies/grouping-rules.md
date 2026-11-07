# Grouping rules for technology pages

- **Scope:** Technology-specific knowledge: when do I open a technology, a facet or a page, where does cross-facet content go, and how does it differ from practices and recall?
- **Keywords:** technology, facet, shared, grouping, folder, naming, traps, index, practices, recall, Godot, dotnet
- **Status:** current
- **Updated:** 2026-11-07
- **Sources:** the hub owner's technology-hierarchy decision (2026-11-07); this folder's own index pages

Rule: group technology-specific pages as technology, then facet, then page.

- **Technology** (`technologies/<technology>/`): one folder per tool or platform, such as `godot/` or `dotnet/`. Open it when the work uses that technology.
- **Facet** (`<technology>/<facet>/`): one folder per kind of work inside the technology, chosen by the content (for example game client or libraries). Create a facet folder only when it holds at least two pages. Until then, the page sits directly in the technology folder.
- **Shared facet** (`<technology>/shared/`): what applies to every facet of the technology, such as language traps, test-framework traps and host or OS traps. Put cross-facet content here, not copied into each facet.
- **Page** (`<topic>-traps.md` or `<topic>.md`): one fact per file, rule first, reason second. Each page's Scope names its technology and facet.

Every folder has a `00-<name>-index.md` with a statement, a reading guide and a table of links.

Boundaries:

- Technology pages hold traps for one technology. A rule that holds for every technology belongs in `practices/`.
- A scenario with a date or a symptom belongs in `recall/`. A technology page states the general trap and may point to a recall entry.
- Project-specific rules, item IDs, product names, paths and credentials never go here. Write "a Godot project", not the project's name.
- Facets are not fixed. The owner may rename or merge them later; update the index rows in the same change.
- Technology pages are labelled with the version they were observed on, because behaviour changes between releases.
