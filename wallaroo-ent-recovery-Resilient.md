# Resilient

```pony
interface tag Resilient
```

## Public Behaviours

### replay_log_entry

```pony
be replay_log_entry(
  uid: U128 val,
  frac_ids: (Array[U32 val] val | None val),
  statechange_id: U64 val,
  payload: (String val | Array[U8 val] val))
```
#### Parameters

*   uid: [U128](builtin-U128) val
*   frac_ids: ([Array](builtin-Array)\[[U32](builtin-U32) val\] val | [None](builtin-None) val)
*   statechange_id: [U64](builtin-U64) val
*   payload: ([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)

---

### initialize_seq_id_on_recovery

```pony
be initialize_seq_id_on_recovery(
  seq_id: U64 val)
```
#### Parameters

*   seq_id: [U64](builtin-U64) val

---

### log_flushed

```pony
be log_flushed(
  low_watermark: U64 val)
```
#### Parameters

*   low_watermark: [U64](builtin-U64) val

---

