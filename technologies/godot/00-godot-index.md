# Godot index

- **Scope:** Technology Godot: which Godot facets and pages exist, and which one should I open for the work at hand?
- **Keywords:** Godot, Godot 4, game engine, GDScript, GUT, Windows, traps, UI, layout, input, web export, game client, game server, shared, facet
- **Status:** current
- **Updated:** 2026-11-07
- **Sources:** the Godot pages' own sources

Godot pages hold traps that are specific to Godot. Each page is labelled with its version. They are not project-invariant rules: check the Godot version you use before applying a trap, because behaviour changes between releases.

Only broadly useful, reusable traps belong here. A project's own scene or code pattern belongs in that project.

Facets are chosen by content:

- [shared/](shared/00-shared-index.md): what applies to every facet, the GDScript language, the GUT test framework and the Windows host.
- [game-client/](game-client/00-game-client-index.md): the player-facing build, its UI, layout, input and Web export.
- Game server: a possible future facet. A server-side Godot project would hold its own traps, but no folder exists yet, because the facet does not hold two pages. Add the folder only when it does.

## Reading guide

- Writing GDScript, or a value is unexpectedly null, false or unparsed: read [shared/gdscript-typing-traps.md](shared/gdscript-typing-traps.md) and [shared/gdscript-async-and-parse-traps.md](shared/gdscript-async-and-parse-traps.md).
- Writing or fixing a GUT test: read [shared/gut-test-traps.md](shared/gut-test-traps.md).
- Running the Godot binary from Git Bash on Windows: read [shared/windows-host-traps.md](shared/windows-host-traps.md).
- Working on Godot 4 UI, layout, input or viewport code: read [game-client/godot-ui-traps.md](game-client/godot-ui-traps.md) first.
- Exporting, serving or verifying a Web build: start at [game-client/00-game-client-index.md](game-client/00-game-client-index.md).
- Any other Godot facet: no page yet.

## Children

| File | What question it answers |
| --- | --- |
| [shared/00-shared-index.md](shared/00-shared-index.md) | Which Godot traps apply to every facet: GDScript, GUT and the Windows host? |
| [game-client/00-game-client-index.md](game-client/00-game-client-index.md) | Which Godot traps apply to the player-facing build: UI, layout, input and Web export? |
