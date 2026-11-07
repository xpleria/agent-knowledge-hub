# Web export toolchain (technology: Godot 4.x, facet: game client, observed on 4.7)

- **Scope:** Technology Godot, facet game client: which editor build and export-template set does a Web export need, and what does Godot refuse when they are wrong?
- **Keywords:** Godot 4, Web export, Mono, .NET, C#, export templates, non-mono, .stable, .stable.mono, APPDATA, export_templates, editor banner, Windows Desktop export, runtime dependency
- **Status:** current
- **Updated:** 2026-11-07
- **Sources:** distilled from a Godot 4.7 project's web-deploy procedure and its toolchain notes; the editor and template paths are the defaults on Windows

A Web export fails for toolchain reasons before any file reaches a host. Check the editor and the templates first, because the error only appears at export time.

1. **Export the Web build from the non-.NET Godot editor.** Godot 4 refuses a Web export from the Mono/C# build, even for a project with no C# code. The refusal says that Web export is not supported in Godot 4 when using C# or .NET. Use the standard editor binary.
   *Reason:* the refusal comes at the end of the build cycle, so a mistake here costs a full attempt.

2. **Give a finder script a way to refuse the Mono build.** A Mono editor announces itself in its banner text. A script that locates the editor can read that banner and refuse the Mono binary, so the wrong editor is never used by accident.

3. **Install the non-mono export templates.** The Web templates belong in the version folder without the mono suffix, for example `<version>.stable/` under the templates directory in the user's application data folder. `<version>.stable.mono/` is a different set, and the two are not interchangeable.
   *Reason:* a mono-only install fails with "No export template found at the expected path", which looks like a missing file rather than a wrong set.

4. **Use the non-mono templates for a desktop export too.** The mono templates add a .NET runtime dependency to the built game. A project with no .NET code has no use for it, so the desktop export has the same template rule.

*Check before the first export:* confirm the editor is the standard build, and confirm the template folder name has no `.mono` suffix. Both checks are cheap; the export is the most expensive way to find out.

## Related

- Headers and hosting that the build needs: see [web-export-headers-and-hosting.md](web-export-headers-and-hosting.md).
- Windows path form for the editor binary: see [windows-host-traps.md](../shared/windows-host-traps.md).
