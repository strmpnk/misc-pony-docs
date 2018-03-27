# FallorMsgDecoder

```pony
primitive val FallorMsgDecoder
```

## Constructors

### create

```pony
new val create()
: FallorMsgDecoder val^
```

#### Returns

* [FallorMsgDecoder](wallaroo_labs-messages-FallorMsgDecoder) val^

---

## Public Functions

### apply

```pony
fun box apply(
  data: Array[U8 val] val)
: Array[String val] val ?
```
#### Parameters

*   data: [Array](builtin-Array)\[[U8](builtin-U8) val\] val

#### Returns

* [Array](builtin-Array)\[[String](builtin-String) val\] val ?

---

### with_timestamp

```pony
fun box with_timestamp(
  data: Array[U8 val] val)
: Array[String val] val ?
```
#### Parameters

*   data: [Array](builtin-Array)\[[U8](builtin-U8) val\] val

#### Returns

* [Array](builtin-Array)\[[String](builtin-String) val\] val ?

---

### eq

```pony
fun box eq(
  that: FallorMsgDecoder val)
: Bool val
```
#### Parameters

*   that: [FallorMsgDecoder](wallaroo_labs-messages-FallorMsgDecoder) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: FallorMsgDecoder val)
: Bool val
```
#### Parameters

*   that: [FallorMsgDecoder](wallaroo_labs-messages-FallorMsgDecoder) val

#### Returns

* [Bool](builtin-Bool) val

---

## Private Functions

### _decode

```pony
fun box _decode(
  data: Array[U8 val] val)
: Array[String val] val ?
```
#### Parameters

*   data: [Array](builtin-Array)\[[U8](builtin-U8) val\] val

#### Returns

* [Array](builtin-Array)\[[String](builtin-String) val\] val ?

---

