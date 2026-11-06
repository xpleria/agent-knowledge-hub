# Relayout must equal a fresh build

- **Scope:** Why did a resized or rotated view differ from one built fresh at the same size, and how is a relayout tested?
- **Keywords:** relayout, fresh build, fresh layout, rotation, resize, minimum height, wrapped label, scaling, per-control rects, orientation
- **Status:** current
- **Source project:** ganvchi-court

## What happened

After a rotation, a few controls kept sizes from the previous layout. A wrapped label kept
the minimum height of its old width, and a base size recorded after scaling was scaled a
second time on reapply. The view looked right at a glance but differed from a fresh build.

## Lesson

- Recompute layout values in the layout pass, not as one-shot values at construction.
- Test a relaid view against a view built fresh at the new size, control by control: compare each rect.
- Pin the scale override for the reference build so both sides use the same scale.
- Cover every profile: portrait to landscape to portrait, and the real fullscreen path. Fullscreen can deliver its size several frames late.

## Why

A relayout that differs from a fresh build is a state the user could not reach by starting
fresh, so it cannot be reasoned about or reproduced.
