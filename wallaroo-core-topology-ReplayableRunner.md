# ReplayableRunner

```pony
trait ref ReplayableRunner
```

## Public Functions

### replay_log_entry

```pony
fun ref replay_log_entry(
  uid: U128 val,
  frac_ids: (Array[U32 val] val | None val),
  statechange_id: U64 val,
  payload: (String val | Array[U8 val] val),
  producer: Producer tag)
: None val
```
#### Parameters

*   uid: [U128](builtin-U128) val
*   frac_ids: ([Array](builtin-Array)\[[U32](builtin-U32) val\] val | [None](builtin-None) val)
*   statechange_id: [U64](builtin-U64) val
*   payload: ([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)
*   producer: [Producer](wallaroo-core-common-Producer) tag

#### Returns

* [None](builtin-None) val

---

### set_step_id

```pony
fun ref set_step_id(
  id: U128 val)
: None val
```
#### Parameters

*   id: [U128](builtin-U128) val

#### Returns

* [None](builtin-None) val

---

