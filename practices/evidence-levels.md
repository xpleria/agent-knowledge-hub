# Evidence levels: what each check proves and what it does not

- **Scope:** Which evidence levels exist for a claim that work is verified, and what does each one fail to prove?
- **Keywords:** evidence level, headless suite, served artefact, deploy transfer, shipped behaviour, runtime check, browser flow interaction, device review, does not prove, overclaim, hash, served bytes
- **Status:** current
- **Updated:** 2026-11-07
- **Sources:** distilled from a Godot project's deploy and verification runs; see also `practices/evidence-and-verification.md` and `project-setup/50-deploy-and-verify-habits.md`

Rule first: report the highest level you actually reached, and name what that level does not prove. Never claim a higher one.

| Level | What it covers | Does not prove |
| --- | --- | --- |
| Headless suite | The tests run in the test runner and their assertions hold. | Rendered output, device behaviour, or that the deployed build matches this tree. |
| Served artefact (deploy transfer) | The file on the host has the expected status, headers and hash of the main file, checked by an independent request. | That the shipped code does what the change claims. HTTP 200 alone proves only that a file exists. |
| Shipped behaviour (runtime check) | The shipped code, called or run as shipped, does what the change claims. | A real browser flow or a device. A text search of a compiled artefact proves nothing here. |
| Browser flow interaction | A real browser drives the route that changed: loads, taps, and transitions, with an empty error log. | Gestures, orientations or device behaviour the browser does not emulate faithfully. |
| Device review | A person or a device on the target hardware carries out the stated steps. | Other devices, orientations or states that were not driven. |

## Rules for the table

- Name the level in every report next to the claim, and list what it does not prove under "not verified".
- A green headless suite verifies its assertions, not the transitions the suite never drives.
- A device review covers only the steps and state it names. An approval of one screen is not an approval of the next.

*Why:* each level answers a different question. A passing suite answers none of the deploy or device questions, and a single "verified" word hides which one was answered.
