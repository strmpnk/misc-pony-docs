# ReplayMsg

```pony
class val ReplayMsg is
  ChannelMsg val
```

#### Implements

* [ChannelMsg](wallaroo-core-messages-ChannelMsg) val

---

## Constructors

### create

```pony
new val create(
  db: Array[(String val | Array[U8 val] val)] val)
: ReplayMsg val^
```
#### Parameters

*   db: [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val

#### Returns

* [ReplayMsg](wallaroo-core-messages-ReplayMsg) val^

---

## Public fields

* let data_bytes: [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val

---

## Public Functions

### data_msg

```pony
fun box data_msg(
  auth: AmbientAuth val)
: DataMsg val ?
```
#### Parameters

*   auth: [AmbientAuth](builtin-AmbientAuth) val

#### Returns

* [DataMsg](wallaroo-core-messages-DataMsg) val ?

---

