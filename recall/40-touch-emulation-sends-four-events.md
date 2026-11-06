# Touch emulation sends four events for one tap

- **Scope:** Why did one tap on a dialog's scrim also trigger the control behind it, and what must input handling absorb?
- **Keywords:** touch, emulate_mouse_from_touch, emulated mouse, pointer, press, release, scrim, dialog, modal, absorb, click-through
- **Status:** current
- **Source project:** ganvchi-court

## What happened

On a touch device, a tap on the scrim closed a modal on the first event. The remaining
events reached the button behind it, which fired. The bug did not reproduce with a mouse.

## Lesson

- One touch arrives as four events: mouse press, touch press, mouse release, touch release. Confirm this for the engine version you use.
- A dismiss action must absorb every pointer press and release until all pointers are up, not only the first.
- Test with a button and a card under the modal, then confirm they work normally after it closes.
- Use a real pointer event in the test; a direct signal emission does not test routing.

## Why

Input that reaches a control while a dialog is closing produces a click the player never
meant to make.
