# Deploy and verify habits

- **Scope:** How should a project deploy and prove a deploy is live, without leaking secrets or trusting a status code alone?
- **Keywords:** deploy, verify, served hash, SHA-256, HTTP 200, evidence level, FTPS, certificate, secrets, env file, gitignore, known state, commit before deploy, cache, no-store, rollback, dry run, versioning, version source, release channel, dev channel, release guard, annotated tag, changelog, build stamp, release date, served label
- **Status:** current
- **Updated:** 2026-11-03
- **Sources:** distilled from a Godot web deploy's procedure and lessons, and its versioning and release procedure (ganvchi-court); engine-specific deploy traps are in `engines/`

## Before deploying

- Deploy from a known state. If the working tree holds someone else's uncommitted work, say so and let the owner choose.
- Commit before the deploy, so each item is visible on its own. A deploy changes no code and creates no commit.
- Run the project's own deploy script. Do not hand-type upload steps.
- Offer a dry-run mode that builds and checks artefacts without credentials or upload.

## Secrets

- Keep credentials in a gitignored env file. The deploy script reads it as data and never prints it.
- Do not source the env file into a shell, and do not pass secrets as command-line arguments, which show up in process lists.
- Use certificate-verified encrypted transfer. Never fall back to plain transfer or disable verification. If the certificate does not match the host name, find the provider's canonical host name.

## Proving a deploy

Evidence levels. Each proves only itself; report the level you reached, never a higher one.

1. **Served bytes.** The artefact is on the host: status, headers and a hash of the main file match the local copy.
2. **Shipped behaviour.** The shipped code does what the change claims. A text search of a compiled artefact proves nothing; call the shipped code.
3. **Browser render.** The page loads, the required isolation or security headers are present, the error overlay is empty, and the canvas or view has real content. Drive the route that changed.
4. **Device interaction.** Gestures and transitions are proven only by driving them on a device.

HTTP 200 alone proves only that a file exists.

## Caching

- Send a no-store cache policy for the main entry and the main artefact, or players stay on an old build after a correct deploy.
- Verify headers by their effect on the responses. Some servers refuse to serve their own configuration file, so do not try to fetch it back.

## Transient failures

- A transient upload error is retried with the same script and the same transport. Then verify the served hash again. See `recall/80-transient-ftp-451-retry.md`.
- Do not skip the deploy or switch to an insecure method to get around a transient error.

## Versioning and channels

- **One version source.** Keep the version in one project setting that the build reads. The on-screen label, the footer and the build stamp all read from it; never keep a second copy. Why: two copies drift, and the label then names a version the build does not have.
- **Give unreleased builds their own path.** Serve the dev or test build from a sub-path (for example `/dev/`) and reserve the root for tagged releases. Why: testers can check a build without replacing the released one.
- **Guard the release upload.** The release step refuses to upload unless the tree is clean, `HEAD` carries the matching annotated tag, and the changelog has a dated section for that version. A dry-run mode runs the same checks without uploading. Why: a release is a named, reproducible state, and a refusal is cheaper than a bad upload.
- **Set the release date at tag preparation.** Until then the changelog heading reads a placeholder such as `TBD`. Why: the date belongs to the act of releasing; a date written earlier is wrong if the release slips.
- **Generate the build stamp, and remove it on exit.** A dev build can stamp the short git hash into a generated file. The file is gitignored and deleted when the build tool exits. Why: a leftover generated file either leaks into a commit or leaves the tree dirty for the next run.
- **Read the label from the built output.** Check the version label in the artefact that was served or exported, not in the source setting. Why: the source can name one version while the build holds another.
