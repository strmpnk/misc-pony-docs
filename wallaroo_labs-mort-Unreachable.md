# Unreachable

`Fail` with a more explicit message. To be used with code that should fail
if it reaches an "unreachable" point.


```pony
primitive val Unreachable
```

## Constructors

### create

```pony
new val create()
: Unreachable val^
```

#### Returns

* [Unreachable](wallaroo_labs-mort-Unreachable) val^

---

## Public Functions

### apply

```pony
fun box apply(
  loc: SourceLoc val = seq)
: None val
```
#### Parameters

*   loc: [SourceLoc](builtin-SourceLoc) val = seq

#### Returns

* [None](builtin-None) val

---

### eq

```pony
fun box eq(
  that: Unreachable val)
: Bool val
```
#### Parameters

*   that: [Unreachable](wallaroo_labs-mort-Unreachable) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: Unreachable val)
: Bool val
```
#### Parameters

*   that: [Unreachable](wallaroo_labs-mort-Unreachable) val

#### Returns

* [Bool](builtin-Bool) val

---

