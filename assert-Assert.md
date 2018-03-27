# Assert

This is a debug only assertion. If the test is false, it will print any
supplied error message to stderr and raise an error.


```pony
primitive val Assert
```

## Constructors

### create

```pony
new val create()
: Assert val^
```

#### Returns

* [Assert](assert-Assert) val^

---

## Public Functions

### apply

```pony
fun box apply(
  test: Bool val,
  msg: String val = seq)
: None val ?
```
#### Parameters

*   test: [Bool](builtin-Bool) val
*   msg: [String](builtin-String) val = seq

#### Returns

* [None](builtin-None) val ?

---

### eq

```pony
fun box eq(
  that: Assert val)
: Bool val
```
#### Parameters

*   that: [Assert](assert-Assert) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: Assert val)
: Bool val
```
#### Parameters

*   that: [Assert](assert-Assert) val

#### Returns

* [Bool](builtin-Bool) val

---

