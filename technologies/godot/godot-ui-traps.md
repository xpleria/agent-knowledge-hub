# Godot 4 UI traps (engine: Godot 4.x, observed on 4.7)

- **Scope:** Which Godot 4 UI, layout, input and viewport behaviours are broadly useful to remember, and what is the safe pattern for each?
- **Keywords:** Godot 4, GDScript, Control, Container, minimum size, queue_free, remove_child, CanvasLayer, z_index, touch emulation, emulate_mouse_from_touch, SubViewport, headless, outline_size, StyleBoxFlat, modulate, Label autowrap, lambda capture, get_minimum_size, custom_minimum_size
- **Status:** current
- **Updated:** 2026-11-07
- **Sources:** distilled from a Godot 4.7 project's pitfall notes and recall entries; engine behaviour should be re-checked on other Godot versions

## Nodes and layout

1. **`queue_free()` keeps the node in the tree until the frame ends.** Call `remove_child(child)` before `child.queue_free()`, or a rebuild measures the old tree.
2. **`add_child` on a node that already has a parent errors.** Detach reused nodes first, and remove a node from its actual `get_parent()`.
3. **Containers sort their children deferred.** Sizes read straight after a change are stale; wait a frame or read the value after the layout pass.
4. **Labels lag a frame, and an autowrap label in a minimum-size container can collapse to a sliver.** Measure text with `Font.get_string_size()`, and test the rendered outcome, not the `autowrap_mode` flag.
5. **A container reports its child's minimum size.** Adding an icon grows the row and shifts centred siblings. Give icon slots a fixed-size plain `Control` and centre the child by anchors.
6. **Rendered control sizes round up to whole pixels.** Floor computed sizes that must fit a band exactly.
7. **`get_minimum_size()` cannot be overridden from GDScript.** Set `custom_minimum_size` instead.
8. **Relayout must equal a fresh build.** Wrapped labels keep a stale minimum height, and a base size recorded after scaling can be scaled twice. Compare per-control rects with a fresh layout.

## Overlays and input

9. **`z_index` orders only siblings.** Put each modal in its own `CanvasLayer` above the content, and test both draw order and that a click reaches it.
10. **A Control's child canvas items draw above its `_draw()`.** An overlay painted in `_draw` sits under the children; keep the overlay as the last child.
11. **`emulate_mouse_from_touch` is on by default.** One touch arrives as four events: mouse press, touch press, mouse release, touch release. Absorb all of them, so a dialog that closed on the first does not leak the rest to the control behind.
12. **A `Button` has no disabled-changed signal.** Poll the `disabled` property, or route changes through a setter.
13. **`emit_signal` does not test input routing.** Push a real `InputEventMouseButton` through the viewport.
14. **A signal must be connected before the transition you want to observe.**

## Drawing and viewports

15. **`modulate` applies per draw call, not as a group fade.** Overlapping translucent children each fade on their own. Use a `CanvasGroup` for an exact group fade.
16. **`outline_size` and `StyleBoxFlat` border widths are whole pixels.** A half-pixel step quantises to nothing; add at least one whole pixel.
17. **A `SubViewport` does not apply canvas stretch, and `get_viewport()` may be null in `_ready`.** Lay out at the target design size inside the viewport, and defer work that needs it.
18. **A headless run reports a zero-size screen and renders no pixels.** Headless results are layout measurements, not device measurements.
19. **A full-rect control under a `SubViewport` has zero size** unless its host has an explicit size and anchors are set after `add_child`.

## Language

20. **A lambda captures local variables by value.** A counter incremented inside a lambda stays 0. Accumulate into a member variable or a reference-typed container.
21. **`-1 % 2 == -1` in GDScript.** Validate an index range instead of relying on modulo for negatives.
22. **A parse error silently drops a test file from the run.** Check the collected test count, and run a parse check on each script.
