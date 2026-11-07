# Web export headers, cache and upload (technology: Godot 4.x, facet: game client, observed on 4.7)

- **Scope:** Technology Godot, facet game client: which HTTP headers, cache settings and upload checks does a threaded Web export need on the host, and what does a host that lacks them look like?
- **Keywords:** Godot 4, Web export, threaded wasm, SharedArrayBuffer, cross-origin isolation, COOP, COEP, Cross-Origin-Resource-Policy, Cache-Control, no-store, Apache, .htaccess, 403, FTPS, 451, hash read-back, served headers
- **Status:** current
- **Updated:** 2026-11-07
- **Sources:** distilled from a Godot 4.7 project's web-deploy notes and its host procedure; header names are the browser standard, the Apache lines are an example

A Web export that is correct on disk can still fail on the host. These three rules are about what the host sends and what the browser keeps.

1. **Serve the cross-origin isolation headers with the build.** A threaded wasm build needs `SharedArrayBuffer`, which browsers expose only to a cross-origin-isolated page. Send `Cross-Origin-Opener-Policy: same-origin` and `Cross-Origin-Embedder-Policy: require-corp` on the HTML and the pack, as in this Apache example:

   ```apache
   Header always set Cross-Origin-Opener-Policy "same-origin"
   Header always set Cross-Origin-Embedder-Policy "require-corp"
   ```

   *Reason:* without them the page returns 200, loads, and then halts at startup with a message that Cross-Origin Isolation or SharedArrayBuffer is missing. That looks like a successful deploy.

2. **Do not turn off thread support to get past the halt.** Disabling threads in the export hides a server misconfiguration behind a downgrade. Fix the headers on the host instead.

3. **Give cross-origin subresources their own policy.** Same-origin subresources are exempt from `require-corp`. A wasm or pack served from another origin also needs a `Cross-Origin-Resource-Policy` header, which a plain isolation setup does not send.

4. **Send no-store on the build files.** Serve `.pck`, `.wasm`, `.js` and `.html` with `Cache-Control: no-store, must-revalidate`, `Pragma: no-cache` and `Expires: 0`.
   *Reason:* without them, a browser can revalidate successfully and keep running the previous pack after a deploy. A deploy can then be correct by hash and still show the old build to returning visitors.

5. **Upload the host header file with the build, and verify it by its effect.** Settings that a build depends on belong with the build, not in a hosting panel that a later deploy may not touch. Apache refuses to serve `.htaccess` itself with a 403, so it cannot be fetched back and compared. Check the response headers of the HTML and the pack instead.

6. **A first FTPS upload may fail with 451 on the pack.** The recovery is a full redeploy, followed by a read-back of the served pack's SHA-256, compared with the local export. A matching hash is the proof; a 200 alone is not.

## Related

- The toolchain that produces the build: see [web-export-toolchain.md](web-export-toolchain.md).
- What a served check does and does not prove: see [web-runtime-checks.md](web-runtime-checks.md).
- Evidence levels in general: see [practices/evidence-levels.md](../../../practices/evidence-levels.md).
