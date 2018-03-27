# EventLog

```pony
actor tag EventLog
```

## Constructors

### create

```pony
new tag create(
  event_log_config: EventLogConfig val = seq)
: EventLog tag^
```
#### Parameters

*   event_log_config: [EventLogConfig](wallaroo-ent-recovery-EventLogConfig) val = seq

#### Returns

* [EventLog](wallaroo-ent-recovery-EventLog) tag^

---

## Public fields

* var num_encoded: [USize](builtin-USize) val

---

## Public Behaviours

### set_router_registry

```pony
be set_router_registry(
  router_registry: RouterRegistry tag)
```
#### Parameters

*   router_registry: [RouterRegistry](wallaroo-ent-router_registry-RouterRegistry) tag

---

### start_pipeline_logging

```pony
be start_pipeline_logging(
  initializer: LocalTopologyInitializer tag)
```
#### Parameters

*   initializer: [LocalTopologyInitializer](wallaroo-core-initialization-LocalTopologyInitializer) tag

---

### start_log_replay

```pony
be start_log_replay(
  recovery: Recovery tag)
```
#### Parameters

*   recovery: [Recovery](wallaroo-ent-recovery-Recovery) tag

---

### log_replay_finished

```pony
be log_replay_finished()
```

---

### replay_log_entry

```pony
be replay_log_entry(
  producer_id: U128 val,
  uid: U128 val,
  frac_ids: (Array[U32 val] val | None val),
  statechange_id: U64 val,
  payload: (String val | Array[U8 val] val))
```
#### Parameters

*   producer_id: [U128](builtin-U128) val
*   uid: [U128](builtin-U128) val
*   frac_ids: ([Array](builtin-Array)\[[U32](builtin-U32) val\] val | [None](builtin-None) val)
*   statechange_id: [U64](builtin-U64) val
*   payload: ([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)

---

### initialize_seq_ids

```pony
be initialize_seq_ids(
  seq_ids: HashMap[U128 val, U64 val, HashEq[U128 val] val] val)
```
#### Parameters

*   seq_ids: [HashMap](collections-HashMap)\[[U128](builtin-U128) val, [U64](builtin-U64) val, [HashEq](collections-HashEq)\[[U128](builtin-U128) val\] val\] val

---

### register_producer

```pony
be register_producer(
  producer: Resilient tag,
  id: U128 val)
```
#### Parameters

*   producer: [Resilient](wallaroo-ent-recovery-Resilient) tag
*   id: [U128](builtin-U128) val

---

### queue_log_entry

```pony
be queue_log_entry(
  producer_id: U128 val,
  uid: U128 val,
  frac_ids: (Array[U32 val] val | None val),
  statechange_id: U64 val,
  seq_id: U64 val,
  payload: Array[(String val | Array[U8 val] val)] val)
```
#### Parameters

*   producer_id: [U128](builtin-U128) val
*   uid: [U128](builtin-U128) val
*   frac_ids: ([Array](builtin-Array)\[[U32](builtin-U32) val\] val | [None](builtin-None) val)
*   statechange_id: [U64](builtin-U64) val
*   seq_id: [U64](builtin-U64) val
*   payload: [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val

---

### flush_buffer

```pony
be flush_buffer(
  producer_id: U128 val,
  low_watermark: U64 val)
```
#### Parameters

*   producer_id: [U128](builtin-U128) val
*   low_watermark: [U64](builtin-U64) val

---

### snapshot_state

```pony
be snapshot_state(
  producer_id: U128 val,
  uid: U128 val,
  statechange_id: U64 val,
  seq_id: U64 val,
  payload: Array[(String val | Array[U8 val] val)] val)
```
#### Parameters

*   producer_id: [U128](builtin-U128) val
*   uid: [U128](builtin-U128) val
*   statechange_id: [U64](builtin-U64) val
*   seq_id: [U64](builtin-U64) val
*   payload: [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val

---

### start_rotation

```pony
be start_rotation()
```

---

### rotate_file

```pony
be rotate_file(
  steps: HashMap[U128 val, Step tag, HashEq[U128 val] val] val)
```
#### Parameters

*   steps: [HashMap](collections-HashMap)\[[U128](builtin-U128) val, [Step](wallaroo-core-topology-Step) tag, [HashEq](collections-HashEq)\[[U128](builtin-U128) val\] val\] val

---

## Public Functions

### write_log

```pony
fun ref write_log()
: None val
```

#### Returns

* [None](builtin-None) val

---

### rotation_complete

```pony
fun ref rotation_complete()
: None val
```

#### Returns

* [None](builtin-None) val

---

## Private Functions

### _queue_log_entry

```pony
fun ref _queue_log_entry(
  producer_id: U128 val,
  uid: U128 val,
  frac_ids: (Array[U32 val] val | None val),
  statechange_id: U64 val,
  seq_id: U64 val,
  payload: Array[(String val | Array[U8 val] val)] val,
  force_write: Bool val = seq)
: None val
```
#### Parameters

*   producer_id: [U128](builtin-U128) val
*   uid: [U128](builtin-U128) val
*   frac_ids: ([Array](builtin-Array)\[[U32](builtin-U32) val\] val | [None](builtin-None) val)
*   statechange_id: [U64](builtin-U64) val
*   seq_id: [U64](builtin-U64) val
*   payload: [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val
*   force_write: [Bool](builtin-Bool) val = seq

#### Returns

* [None](builtin-None) val

---

### _flush_buffer

```pony
fun ref _flush_buffer(
  producer_id: U128 val,
  low_watermark: U64 val)
: None val
```
#### Parameters

*   producer_id: [U128](builtin-U128) val
*   low_watermark: [U64](builtin-U64) val

#### Returns

* [None](builtin-None) val

---

### _rotate_file

```pony
fun ref _rotate_file()
: None val
```

#### Returns

* [None](builtin-None) val

---

