# Fact

This is an assertion that is always enabled. If the test is false, it will
print any supplied error message to stderr and raise an error.


```pony
primitive val Fact
```

## Constructors

### create

```pony
new val create()
: Fact val^
```

#### Returns

* [Fact](assert-Fact) val^

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
  that: Fact val)
: Bool val
```
#### Parameters

*   that: [Fact](assert-Fact) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: Fact val)
: Bool val
```
#### Parameters

*   that: [Fact](assert-Fact) val

#### Returns

* [Bool](builtin-Bool) val

---

