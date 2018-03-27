# LazyInvariant

This is a debug only assertion. If the test is false or throws an error,
it will print 'Invariant violated' along with the source file location
of the invariant to stderr and then forcibly exit the program.


```pony
primitive val LazyInvariant is
  _InvariantFailure ref
```

#### Implements

* [_InvariantFailure](wallaroo-core-invariant-_InvariantFailure) ref

---

## Constructors

### create

```pony
new val create()
: LazyInvariant val^
```

#### Returns

* [LazyInvariant](wallaroo-core-invariant-LazyInvariant) val^

---

## Public Functions

### apply

```pony
fun box apply(
  f: {(): Bool ?} ref,
  loc: SourceLoc val = seq)
: None val
```
#### Parameters

*   f: {(): Bool ?} ref
*   loc: [SourceLoc](builtin-SourceLoc) val = seq

#### Returns

* [None](builtin-None) val

---

### fail

```pony
fun box fail(
  loc: SourceLoc val)
: None val
```
#### Parameters

*   loc: [SourceLoc](builtin-SourceLoc) val

#### Returns

* [None](builtin-None) val

---

### eq

```pony
fun box eq(
  that: LazyInvariant val)
: Bool val
```
#### Parameters

*   that: [LazyInvariant](wallaroo-core-invariant-LazyInvariant) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: LazyInvariant val)
: Bool val
```
#### Parameters

*   that: [LazyInvariant](wallaroo-core-invariant-LazyInvariant) val

#### Returns

* [Bool](builtin-Bool) val

---

