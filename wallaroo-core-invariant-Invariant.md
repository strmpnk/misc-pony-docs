# Invariant

This is a debug only assertion. If the test is false, it will print
'Invariant violated' along with the source file location of the
invariant to stderr and then forcibly exit the program.


```pony
primitive val Invariant is
  _InvariantFailure ref
```

#### Implements

* [_InvariantFailure](wallaroo-core-invariant-_InvariantFailure) ref

---

## Constructors

### create

```pony
new val create()
: Invariant val^
```

#### Returns

* [Invariant](wallaroo-core-invariant-Invariant) val^

---

## Public Functions

### apply

```pony
fun box apply(
  test: Bool val,
  loc: SourceLoc val = seq)
: None val
```
#### Parameters

*   test: [Bool](builtin-Bool) val
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
  that: Invariant val)
: Bool val
```
#### Parameters

*   that: [Invariant](wallaroo-core-invariant-Invariant) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: Invariant val)
: Bool val
```
#### Parameters

*   that: [Invariant](wallaroo-core-invariant-Invariant) val

#### Returns

* [Bool](builtin-Bool) val

---

