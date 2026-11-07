# Godot shared facet index

- **Scope:** Technology Godot, facet shared: which Godot traps apply to every facet of the technology (language, test framework and host), and which page holds each?
- **Keywords:** Godot, shared, GDScript, GUT, Windows, Git Bash, traps, index, facet, cross-facet
- **Status:** current
- **Updated:** 2026-11-07
- **Sources:** the Godot pages' own sources; the hub's grouping rules

A shared facet holds what applies to every facet of Godot: the language, the test framework and the host. It is not a place for one kind of game work. A trap that is true only for the game client belongs in that facet, and a trap that is true for every facet belongs here once, not copied into each facet.

These pages are labelled with the Godot version they were observed on. Engine and language behaviour changes between releases, so check the version you use before you apply a trap.

## Reading guide

- Writing typed GDScript, or a value is unexpectedly null, false or unparsed: read [gdscript-typing-traps.md](gdscript-typing-traps.md).
- A coroutine freezes, a file drops out of a run, or a script fails to parse or import: read [gdscript-async-and-parse-traps.md](gdscript-async-and-parse-traps.md).
- Writing or fixing a GUT test, or a teardown leaks state: read [gut-test-traps.md](gut-test-traps.md).
- Running the Godot binary from Git Bash on Windows, or a save fails: read [windows-host-traps.md](windows-host-traps.md).

## Children

| File | What question it answers |
| --- | --- |
| [gdscript-typing-traps.md](gdscript-typing-traps.md) | Which typed-array, truthiness, inference and class-export behaviours in GDScript break silently? (Godot 4.x, observed on 4.7.) |
| [gdscript-async-and-parse-traps.md](gdscript-async-and-parse-traps.md) | Which await, parse, preload, JSON and import behaviours freeze, drop or rot a script? (Godot 4.x, observed on 4.7.) |
| [gut-test-traps.md](gut-test-traps.md) | Which GUT test habits let a test pass with nothing asserted, or leak into the next test? (Godot 4.x with GUT, observed on 4.7.) |
| [windows-host-traps.md](windows-host-traps.md) | Which path form does a Windows Godot binary need when it is run from Git Bash? (Observed on Windows with Git Bash.) |
