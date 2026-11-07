# GDScript typing traps (technology: Godot 4.x, facet: shared, observed on 4.7)

- **Scope:** Technology Godot, facet shared (applies to every facet): which GDScript static-typing, value and class behaviours have caught a Godot project out, and what is the safe pattern for each?
- **Keywords:** GDScript, static typing, typed Array, Array.assign, str(false), truthy, Variant, type inference, typed export, inner class, .tres, sub-resource, monkey-patch, subclass, built-in method, Godot 4
- **Status:** current
- **Updated:** 2026-11-07
- **Sources:** distilled from a Godot 4.7 project's pitfall notes and its failed-test write-ups; engine behaviour should be re-checked on other Godot versions

Typing mistakes in GDScript often do not stop the program. They turn into a refusal, a null or a gated check that never runs. Check the type at the boundary, and assert the outcome, not the flag.

## Typed collections and values

1. **Pass a typed `Array[T]` only a typed array.** An untyped nested `Array` passed to an `Array[T]` parameter raises a runtime error. Inside a guard, that error looks like an ordinary refusal, so a missing feature reads as a rule decision. Build a typed copy with `typed.assign(untyped)` and pass that.

2. **`str(false)` is the non-empty string `"false"`, which is truthy.** An assertion gated on the string form of a value never fires when the value is false. Test the bool itself, and compare with the literal you expect.

3. **Annotate any variable derived from a `Variant`.** `var x := dict.keys().max()` does not parse, because the type cannot be inferred from a `Variant`. The same applies to anything taken from a script loaded with `load()`. Write the type explicitly, for example `var x: int = dict.keys().max()`.

## Classes and exports

4. **A built-in method on a typed object cannot be monkey-patched.** Assigning a `func` to a method of a typed built-in object is illegal. Subclass the type, override the method and record the calls in the override instead.

5. **A typed export whose type is an inner class loads as `null` from a `.tres` sub-resource** (observed on Godot 4.7). The file loads without error and the property is simply null. Make every such group a top-level script with a class name.
   *Check:* after changing an export, load the resource in a test and assert the property is not null, unconditionally.

## Related

- Lambdas capture locals by value, and `-1 % 2 == -1`: see [godot-ui-traps.md](../game-client/godot-ui-traps.md), items 20 and 21.
- Parse errors, `await`, preload closures and JSON errors: see [gdscript-async-and-parse-traps.md](gdscript-async-and-parse-traps.md).
- Test-framework consequences of these traps: see [gut-test-traps.md](gut-test-traps.md).
