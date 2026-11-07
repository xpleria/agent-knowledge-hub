# Web export runtime checks and evidence (technology: Godot 4.x, facet: game client, observed on 4.7)

- **Scope:** Technology Godot, facet game client: what does each check of a deployed Web build prove, and how do you check that a fix is live in the shipped code?
- **Keywords:** Godot 4, Web export, release pack, index.pck, GDScript bytecode, grep, version label, compressed pack, crossOriginIsolated, status overlay, canvas, headless Chromium, CDP, runtime check, evidence level
- **Status:** current
- **Updated:** 2026-11-07
- **Sources:** distilled from a Godot 4.7 project's web verification notes and deploy evidence; the evidence levels follow the hub's evidence page

A deployed build can be served, uploaded and hash-matched and still not run the change. Each check below proves one thing; report the level you reached, and no higher.

1. **Ask whether a fix is live by calling the shipped code.** A release export stores GDScript as bytecode, so a text search of the pack for a function name reports it missing every time, whether or not the code is there. Mount the deployed pack in a throwaway project and call the function, then read the result.

2. **Read the version label from the build output or a browser render, not from the pack bytes.** The label is computed from the compressed pack, so grep finds no version string in `index.pck`. A search for the label proves nothing about the label.

3. **A browser runtime check needs three conditions.** The deployed page must show that cross-origin isolation is true, that the engine's status overlay is empty, and that the canvas has real content, not a blank frame. Only all three together count as "running".

4. **A render proves only the route it shows.** A screenshot of the menu proves the menu. Drive the route that changed, such as the screen the fix touches, and check the three conditions there.

5. **Use a headless Chromium over CDP as a fallback, and report it as a runtime check only.** When the hosted browser tool is unavailable, for example at session creation or when the local profile is locked, a headless Chromium driven over CDP with a scratch profile can check the three conditions. Record the engine's startup version line as part of the run. Flow and device checks stay open.

## Related

- Browser values that a headless run cannot supply: see [web-browser-values-and-scaling.md](web-browser-values-and-scaling.md).
- Evidence levels in general: see [practices/evidence-levels.md](../../../practices/evidence-levels.md).
