# Invariant package

Wallaroo specific variation on the standard Pony `Assert` functionality.
Wraps our usual assertion logic into a new clean primitive.

For most invariant, you want to use the `Invariant` primitive. It handles
standard invariants such as:

```pony
Invariant(this_value > that_value)
Invariant(map.contains(key))
```

Some invariants those are more complicated. Let's take the case of the
a map where we need to look up a value and then determine if that value
is above a certain number. Because `map(key) > other_value` can throw
an error if `key` isn't in `map`, we can't use `Invariant` without
wrapping it in a `try .. else .. end` block. When you have such a
scenario, reach for `LazyInvariant`.

Rather than taking a `Bool` value for testing, `LazyInvariant` takes
a lambda expression returns a `Bool`. If the expression fails or if it
throws an error, `LazyInvariant` will fail.

```pony
LazyInvariant({()(map, key, other_value): Bool ? =>
  map(key) >= other_value})
```


## Public Types

* [primitive Invariant](wallaroo-core-invariant-Invariant.md)
* [primitive LazyInvariant](wallaroo-core-invariant-LazyInvariant.md)


## Private Types

* [trait _InvariantFailure](wallaroo-core-invariant-_InvariantFailure.md)
