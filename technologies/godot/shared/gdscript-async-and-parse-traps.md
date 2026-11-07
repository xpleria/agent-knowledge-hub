# GDScript async, parse and resource traps (technology: Godot 4.x, facet: shared, observed on 4.7)

- **Scope:** Technology Godot, facet shared (applies to every facet): which GDScript coroutine, parse, preload, JSON and resource-import behaviours have caught a Godot project out, and what is the safe pattern for each?
- **Keywords:** GDScript, await, coroutine, parse error, real_ prefix, preload, const, --check-only, dependency closure, load(), JSON.parse_string, JSON.new, engine error, res://, .uid sidecar, import, probe, Godot 4
- **Status:** current
- **Updated:** 2026-11-07
- **Sources:** distilled from a Godot 4.7 project's pitfall notes and its verification write-ups; engine behaviour should be re-checked on other Godot versions

These traps fail quietly: a frozen screen, a file that drops out of a run, or a script that rots without a failure. Each one needs a check that would notice it.

## Coroutines

1. **Await only a function that really suspends.** A helper that contains `await` can return without suspending, for example in an instant mode that turns every wait into zero. Awaiting that helper parks the caller, the coroutine never resumes and the screen freezes with no error. Read the duration first and branch synchronously when it is zero. Do not await a helper in a path where it may return at once.

## Parsing

2. **A local name that starts with a built-in type prefix can stop the file parsing.** A local named `real_seconds` collides with the `real_` type prefix, and the whole file fails to parse. Choose local names that do not begin with a built-in type prefix.

3. **A parse error silently drops a test file from a test run.** The test count simply does not rise. Check the collected count after each change, and parse-check each script on its own (see [gut-test-traps.md](gut-test-traps.md), item 6).

## Dependencies and preload

4. **A `const` preload pulls the target into the compile-time dependency closure.** Preloading a script that uses a scene made the `--check-only` run of one script re-enter that scene and fail with "referenced non-existent resource". Load such scripts at runtime with `load()`. If the error persists after that, suspect a stale `.godot` import or export cache, and clear it once, not repeatedly.

## Engine messages and JSON

5. **`JSON.parse_string()` prints an engine error on malformed input.** A test of malformed input then fails, because the test framework counts the printed error as a failure. Where malformed input is a handled case, create a `JSON` instance, call its `parse()` method and read the returned error code. Trusted asset reads may keep the convenience function.

## Resource import

6. **Scripts inside `res://` are imported, and their `.uid` sidecars rot.** Godot creates a `.uid` sidecar for every script in the project tree, including throwaway probes in a documentation folder. A test runner's parse check may not see them, so they go stale without a failure. Keep probes outside the project tree, or delete them after use.

## Related

- Typed arrays, `str(false)` and inference: see [gdscript-typing-traps.md](gdscript-typing-traps.md).
- Await in a UI test and orphan nodes: see [gut-test-traps.md](gut-test-traps.md), item 4.
