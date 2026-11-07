# Godot game-client facet index

- **Scope:** Technology Godot, facet game client: which Godot pages cover the client's UI, layout and input, and its Web export, and which one should I open?
- **Keywords:** Godot, game client, UI, layout, Control, input, Web export, export templates, headers, hosting, runtime check, browser, licence, PWA, index
- **Status:** current
- **Updated:** 2026-11-07
- **Sources:** the Godot pages' own sources; the hub's grouping rules

The game-client facet holds Godot traps for the player-facing build: the UI and its layout, and the Web export that ships it. Each page is labelled with the Godot version it was observed on. Check that version before you apply a trap, because engine behaviour changes between releases.

Traps that every facet shares, such as GDScript typing or GUT, are in [shared/](../shared/00-shared-index.md). Link to them; do not copy them here.

## Reading guide

- Writing UI, layout, input or viewport code: read [godot-ui-traps.md](godot-ui-traps.md) first.
- Preparing a Web export or its toolchain: read [web-export-toolchain.md](web-export-toolchain.md).
- Serving the build, or a host or upload failure: read [web-export-headers-and-hosting.md](web-export-headers-and-hosting.md).
- Checking that a deployed build runs, and what a check proves: read [web-runtime-checks.md](web-runtime-checks.md).
- Scaling to the browser, or testing a web-only expression: read [web-browser-values-and-scaling.md](web-browser-values-and-scaling.md).
- Stale builds on returning visitors, or a licence missing from the build: read [web-persistence-and-licences.md](web-persistence-and-licences.md).

## Children

| File | What question it answers |
| --- | --- |
| [godot-ui-traps.md](godot-ui-traps.md) | Which Godot 4 UI, layout, input and viewport behaviours have caught projects out, and what is the safe pattern? (Godot 4.x, observed on 4.7.) |
| [web-export-toolchain.md](web-export-toolchain.md) | Which editor build and export templates does a Web export need, and what does Godot refuse? (Godot 4.x, observed on 4.7.) |
| [web-export-headers-and-hosting.md](web-export-headers-and-hosting.md) | Which headers, cache settings and upload checks does a threaded Web build need on the host? (Godot 4.x, observed on 4.7.) |
| [web-runtime-checks.md](web-runtime-checks.md) | What does each check of a deployed Web build prove, and how is a fix shown to be live? (Godot 4.x, observed on 4.7.) |
| [web-browser-values-and-scaling.md](web-browser-values-and-scaling.md) | How does a Web build read browser size and preferences, and how is a web-only expression tested? (Godot 4.x, observed on 4.7.) |
| [web-persistence-and-licences.md](web-persistence-and-licences.md) | What does a Web deploy leave on the host, and how do bundled licence texts reach the build? (Godot 4.x, observed on 4.7.) |
