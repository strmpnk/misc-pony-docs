# BoolConverter

```pony
primitive val BoolConverter
```

## Constructors

### create

```pony
new val create()
: BoolConverter val^
```

#### Returns

* [BoolConverter](wallaroo_labs-conversions-BoolConverter) val^

---

## Public Functions

### bool_to_u8

```pony
fun box bool_to_u8(
  x: Bool val)
: U8 val
```
#### Parameters

*   x: [Bool](builtin-Bool) val

#### Returns

* [U8](builtin-U8) val

---

### u8_to_bool

```pony
fun box u8_to_bool(
  x: U8 val)
: Bool val
```
#### Parameters

*   x: [U8](builtin-U8) val

#### Returns

* [Bool](builtin-Bool) val

---

### eq

```pony
fun box eq(
  that: BoolConverter val)
: Bool val
```
#### Parameters

*   that: [BoolConverter](wallaroo_labs-conversions-BoolConverter) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: BoolConverter val)
: Bool val
```
#### Parameters

*   that: [BoolConverter](wallaroo_labs-conversions-BoolConverter) val

#### Returns

* [Bool](builtin-Bool) val

---

