# Screenshots and testing discipline

- **Scope:** How should an agent capture, view and describe screenshots and test renders so the owner can trust them?
- **Keywords:** screenshot, capture, render, real background, device size, phone size, zoomed crop, annotation, vision review, blank render, unrepresentative, headless, device steps, orientation
- **Status:** current
- **Updated:** 2026-11-07
- **Sources:** distilled from a Godot project's capture and review practice

## Rules

- Render on the real background the product uses, not a placeholder or a legacy theme. Say which background a capture used.
- Capture at real device sizes, including the supported minimum width, in both orientations.
- Add a zoomed crop of each small detail under review, and an annotated copy with the defect boxed.
- View every image yourself and describe what it shows. A blank or unrepresentative render is reported as such, not shipped.
- Write captures to a new, uniquely named folder for each item. Remove single files, not folders, with plain commands.
- Save the capture command and its output next to the images, so the capture can be re-run.

## Headless is not a device

- A headless render gives layout numbers, not device pixels. Say so in the report.
- For a defect that appears only on a device, ask the owner for before-and-after screenshots at the same state, with the seat, orientation and route, before guessing a cause.
- Give the owner exact device steps for each check.

## Sending evidence

- Send images with their file paths and a one-line description each.
- State any limitation next to the image: a crop, a scaled render, a missing element.
