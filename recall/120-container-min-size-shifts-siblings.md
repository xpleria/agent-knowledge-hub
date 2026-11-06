# Adding an icon moved its neighbours

- **Scope:** Why did adding an icon shift the centred controls next to it, and how is the slot built so siblings stay put?
- **Keywords:** container, minimum size, icon, sibling shift, centred, fixed slot, anchors, overhang, layout shift, rect comparison
- **Status:** current
- **Updated:** 2026-11-01
- **Source project:** ganvchi-court

## What happened

A marker icon was added to a row of centred labels. The row grew to fit the icon, and every
label moved sideways on each seat and orientation.

## Lesson

- A container reports its child's minimum size. A new child changes the row's size.
- Give the icon a plain fixed-size slot, with width and height set, and centre the icon in it by anchors.
- Let the icon overhang its slot if needed. Accepting slight clipping is cheaper than a layout shift.
- Test by comparing a neighbour's rect with and without the icon, for every layout profile.

## Why

Layout shifts are visible to players and look like a regression even when nothing else changed.
