# FallorMsgEncoder

```pony
primitive val FallorMsgEncoder
```

## Constructors

### create

```pony
new val create()
: FallorMsgEncoder val^
```

#### Returns

* [FallorMsgEncoder](wallaroo_labs-messages-FallorMsgEncoder) val^

---

## Public Functions

### apply

[Header | Total size | (String size | String) ... ]


```pony
fun box apply(
  data: (String val | Seq[String val] val),
  wb: Writer ref = seq)
: Array[(String val | Array[U8 val] val)] val
```
#### Parameters

*   data: ([String](builtin-String) val | [Seq](builtin-Seq)\[[String](builtin-String) val\] val)
*   wb: [Writer](buffered-Writer) ref = seq

#### Returns

* [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val

---

### timestamp_raw

```pony
fun box timestamp_raw(
  timestamp: U64 val,
  data: Array[U8 val] val,
  wb: Writer ref = seq)
: Array[(String val | Array[U8 val] val)] val
```
#### Parameters

*   timestamp: [U64](builtin-U64) val
*   data: [Array](builtin-Array)\[[U8](builtin-U8) val\] val
*   wb: [Writer](buffered-Writer) ref = seq

#### Returns

* [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val

---

### eq

```pony
fun box eq(
  that: FallorMsgEncoder val)
: Bool val
```
#### Parameters

*   that: [FallorMsgEncoder](wallaroo_labs-messages-FallorMsgEncoder) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: FallorMsgEncoder val)
: Bool val
```
#### Parameters

*   that: [FallorMsgEncoder](wallaroo_labs-messages-FallorMsgEncoder) val

#### Returns

* [Bool](builtin-Bool) val

---

