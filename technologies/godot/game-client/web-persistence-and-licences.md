# Web persistence and bundled licences (technology: Godot 4.x, facet: game client, observed on 4.7)

- **Scope:** Technology Godot, facet game client: what does a Web deploy leave behind on the host, and how must bundled third-party licence texts reach the build?
- **Keywords:** Godot 4, Web export, progressive web app, PWA, service worker, manifest, stale cache, remote files, FTP, licence, OFL, SIL Open Font License, include_filter, export filter, all_resources, licence texts, About screen
- **Status:** current
- **Updated:** 2026-11-07
- **Sources:** distilled from a Godot 4.7 project's web export preset, its deploy notes and its licence rules; licence obligations are those of the font licences the project bundled

Two things outlive a build in the Web setup: the files a deploy left on the host, and the licence texts a player can reach. Both are easy to lose without an error.

1. **Remove PWA artefacts from the host when PWA is turned off.** Turning on the progressive web app setting emits a manifest and a service worker. A deploy does not delete remote files, so these artefacts stay on the host after the setting is turned off again.
   *Reason:* a returning visitor's browser can keep using the cached service worker and run a stale build, even though the new deploy is correct. Remove the artefacts by hand when turning PWA off.

2. **Treat a PWA change as a deploy change with its own check.** Turning the setting on or off changes what the host holds and what returning visitors run, so it needs the same served-hash and runtime checks as any other deploy.

3. **Bundled third-party licence texts must travel into the build.** A font under the SIL Open Font License must be accompanied by its copyright notice and licence in every copy that bundles it. For a Web export, the only copy a player can reach is the one inside the pack. Store the texts in the project's assets, and show them from an in-game screen such as an About screen.

4. **A plain text file needs an include filter.** A licence `.txt` is not an imported resource, so an export filter of `all_resources` drops it silently. Name the file or folder in the export preset's include filter, and confirm the file is in the built output.

## Related

- Deploy headers and the hash read-back: see [web-export-headers-and-hosting.md](web-export-headers-and-hosting.md).
- Evidence levels for a deploy: see [practices/evidence-levels.md](../../../practices/evidence-levels.md).
