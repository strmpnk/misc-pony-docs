# Fail

'This should never happen' error encountered. Bail out of our running
program. Print where the error happened and exit.


```pony
primitive val Fail
```

## Constructors

### create

```pony
new val create()
: Fail val^
```

#### Returns

* [Fail](wallaroo_labs-mort-Fail) val^

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
  that: Fail val)
: Bool val
```
#### Parameters

*   that: [Fail](wallaroo_labs-mort-Fail) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: Fail val)
: Bool val
```
#### Parameters

*   that: [Fail](wallaroo_labs-mort-Fail) val

#### Returns

* [Bool](builtin-Bool) val

---

