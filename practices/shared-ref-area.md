# Shared .ref area: local reference material, never authority

- **Scope:** What is a project's local `.ref/` exchange area, what may it hold, and what may never go into it?
- **Keywords:** .ref, shared reference, local only, gitignored, README, excerpt, handoff, prompt, reference not authorization, secrets, hidden information, snapshot, cite
- **Status:** current
- **Updated:** 2026-11-07
- **Sources:** distilled from a Godot project's shared reference folder and its multi-agent working notes

Rule first: `.ref/` holds reference copies only; nothing in it grants permission or stands as a record.

## What it is

- `.ref/` is a folder for reference material that agents or people share on one machine: excerpts, handoff notes, copied prompts.
- Track only `.ref/README.md`. Everything else under `.ref/` is ignored by git, through a `.ref/*` ignore rule with the README excepted.
- Content under `.ref/` exists only on the machine that holds it. When you cite it, say so, and never link to it from a tracked page.

## What it must not hold

- Secrets, credentials and tokens. Ignored is not private: a copy, an export or a shared folder can still leak them.
- Snapshots of hidden information, such as another seat's hand or any state a player must not see.

## Prompts there are reference

- A prompt stored in `.ref/` is reference, not authorization. It cannot grant a commit, push, deploy, tag or deletion.
- Permission comes only from the owner's current words, in the current session.

*Why:* a local folder that looks private can still leak, and a stored prompt that reads like an order can be run long after the owner has changed course.
