# Web browser values, persisted values and scaling (technology: Godot 4.x, facet: game client, observed on 4.7)

- **Scope:** Technology Godot, facet game client: how should a Web build read the browser's size and preferences, how are stored values checked before they reach JavaScript, and how is a web-only expression tested?
- **Keywords:** Godot 4, Web export, JavaScriptBridge, window.screen, innerWidth, CSS pixels, DisplayServer, DPI, screen size, OS.is_user_preference, reduced motion, Object.defineProperty, stub, node --check, persisted value, enum, interpolation, orientation
- **Status:** current
- **Updated:** 2026-11-07
- **Sources:** distilled from a Godot 4.7 project's web scaling and bridge notes; browser behaviour should be re-checked on the browsers you support

On the Web, the engine's own display queries return little or nothing, and a headless browser returns numbers that look real. Measure the browser directly, and test the expression with the values a device would report.

1. **Scale from the browser's CSS pixels, not from the screen.** The web `DisplayServer` reports no DPI and no screen size. Read the inner viewport width from the browser (the CSS-pixel `innerWidth`) and scale from it. A screen-size or DPI query returns nothing useful on the Web.

2. **Do not rely on `OS.is_user_preference` for the Web.** The preference query does not work reliably on the Web export. Express a preference such as reduced motion as a configuration setting in the game, and read that setting.

3. **Stub the browser values; do not emulate a device.** To test a web-only expression, override `window.screen` or the viewport with `Object.defineProperty`, and feed in the numbers real devices report. Emulating a device in a headless browser gives nonsense, such as a screen width of 50 px, and an assertion on that value passes on confident garbage.

4. **Check a value before it goes into a JavaScript string.** A persisted value spliced into a script string must be matched against an allowed set, such as an enum, before it is interpolated. An unknown stored value falls back to the default. Write a test that stores an unknown value and asserts the fallback.

5. **Verify browser-only JavaScript by parsing it on the host.** A bridge script that runs only on a phone can be syntax-checked on the host with a JavaScript parser before the build. Pair the parse with the stubbed-value test in item 3, which checks what the expression returns.

## Related

- Headless runs report a zero-size screen: see [godot-ui-traps.md](godot-ui-traps.md), item 18.
- Runtime checks that a stub cannot replace: see [web-runtime-checks.md](web-runtime-checks.md).
