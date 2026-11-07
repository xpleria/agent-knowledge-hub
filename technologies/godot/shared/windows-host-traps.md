# Godot on Windows from a POSIX shell (technology: Godot 4.x, facet: shared, observed on Windows with Git Bash)

- **Scope:** Technology Godot, facet shared (applies to every facet): when a Windows build of the Godot editor or console binary is run from a POSIX shell such as Git Bash, which path form must it receive, and what fails when it does not?
- **Keywords:** Godot console binary, Windows, Git Bash, MSYS, POSIX path, /tmp, err=7, scratch path, path translation, native program, headless, save
- **Status:** current
- **Updated:** 2026-11-07
- **Sources:** distilled from a Godot 4.7 project's evidence notes on running the editor headless from Git Bash on Windows 11

1. **Pass a native Windows Godot binary Windows-style paths.** The Godot console binary is a native Windows program, and it does not receive the translation that a shell applies to its own builtins. Give it `C:/...` or `C:\...` paths, not `/c/...` or `/tmp/...`.
   *Reason:* a POSIX path such as `/tmp/...` is not a file the native program can resolve. On save, the run fails with `err=7`, and the output looks like a Godot failure rather than a path error.

2. **Use a scratch path under the user profile for files the binary must read or write.** Put the file under a folder in the user's profile, for example a scratch folder under the local application data directory, and pass its Windows path. Do not use the POSIX temp directory: it is not the path the binary resolves.
   *Check:* after a headless run that saves a file, read the file back from the shell and confirm that it exists at the Windows path you passed.

3. **Check the path form before reading a failed save as a Godot bug.** A save that fails with `err=7` on Windows is most often the path form. Change the path to the Windows form and re-run the same command before you change the code or the scene.

## Related

- Finding the right editor binary on Windows, and the Mono build refusal: see [web-export-toolchain.md](../game-client/web-export-toolchain.md).
- Headless runs are layout measurements, not device measurements: see [godot-ui-traps.md](../game-client/godot-ui-traps.md), item 18.
