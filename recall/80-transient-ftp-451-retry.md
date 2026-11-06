# Transient FTP 451 on upload: retry the same script

- **Scope:** What should an agent do when a deploy upload fails with a transient 451 error?
- **Keywords:** FTP, FTPS, 451, transient, retry, upload, index.pck, served hash, deploy, transport
- **Status:** current
- **Source project:** ganvchi-court

## What happened

A large file upload failed with a transient "451, local error" response. The first reaction
was to change the upload method. The file was uploaded again by the same script, and the
served hash then matched the local build.

## Lesson

- A 451 response is transient. Rerun the same deploy script, with the same transport.
- Do not switch to plain transfer, disable certificate checks, or skip the deploy.
- After a successful retry, verify the served hash with an independent request. The upload's own success message is not proof.
- If the retry fails again, report the exact error and the hash status. Do not claim the deploy is live.

## Why

Changing the transport to get past a transient error trades a small delay for an
insecure or unverified deploy.
