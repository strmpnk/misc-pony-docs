# DataReceiver

```pony
actor tag DataReceiver is
  Producer tag
```

#### Implements

* [Producer](wallaroo-core-common-Producer) tag

---

## Constructors

### create

```pony
new tag create(
  auth: AmbientAuth val,
  worker_name: String val,
  sender_name: String val,
  initialized: Bool val = seq)
: DataReceiver tag^
```
#### Parameters

*   auth: [AmbientAuth](builtin-AmbientAuth) val
*   worker_name: [String](builtin-String) val
*   sender_name: [String](builtin-String) val
*   initialized: [Bool](builtin-Bool) val = seq

#### Returns

* [DataReceiver](wallaroo-ent-data_receiver-DataReceiver) tag^

---

## Public Behaviours

### start_replay_processing

```pony
be start_replay_processing()
```

---

### start_normal_message_processing

```pony
be start_normal_message_processing()
```

---

### data_connect

```pony
be data_connect(
  sender_step_id: U128 val,
  conn: DataChannel tag)
```
#### Parameters

*   sender_step_id: [U128](builtin-U128) val
*   conn: [DataChannel](wallaroo-core-data_channel-DataChannel) tag

---

### update_watermark

```pony
be update_watermark(
  route_id: U64 val,
  seq_id: U64 val)
```
#### Parameters

*   route_id: [U64](builtin-U64) val
*   seq_id: [U64](builtin-U64) val

---

### update_router

```pony
be update_router(
  router: DataRouter val)
```
#### Parameters

*   router: [DataRouter](wallaroo-core-topology-DataRouter) val

---

### received

```pony
be received(
  d: DeliveryMsg val,
  pipeline_time_spent: U64 val,
  seq_id: U64 val,
  latest_ts: U64 val,
  metrics_id: U16 val,
  worker_ingress_ts: U64 val)
```
#### Parameters

*   d: [DeliveryMsg](wallaroo-core-messages-DeliveryMsg) val
*   pipeline_time_spent: [U64](builtin-U64) val
*   seq_id: [U64](builtin-U64) val
*   latest_ts: [U64](builtin-U64) val
*   metrics_id: [U16](builtin-U16) val
*   worker_ingress_ts: [U64](builtin-U64) val

---

### request_ack

```pony
be request_ack()
```

---

### replay_received

```pony
be replay_received(
  r: ReplayableDeliveryMsg val,
  pipeline_time_spent: U64 val,
  seq_id: U64 val,
  latest_ts: U64 val,
  metrics_id: U16 val,
  worker_ingress_ts: U64 val)
```
#### Parameters

*   r: [ReplayableDeliveryMsg](wallaroo-core-messages-ReplayableDeliveryMsg) val
*   pipeline_time_spent: [U64](builtin-U64) val
*   seq_id: [U64](builtin-U64) val
*   latest_ts: [U64](builtin-U64) val
*   metrics_id: [U16](builtin-U16) val
*   worker_ingress_ts: [U64](builtin-U64) val

---

### dispose

```pony
be dispose()
```

---

### mute

```pony
be mute(
  c: Consumer tag)
```
#### Parameters

*   c: [Consumer](wallaroo-core-common-Consumer) tag

---

### unmute

```pony
be unmute(
  c: Consumer tag)
```
#### Parameters

*   c: [Consumer](wallaroo-core-common-Consumer) tag

---

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

## Public Functions

### init_timer

```pony
fun ref init_timer()
: None val
```

#### Returns

* [None](builtin-None) val

---

### flush

This is not a real Producer, so it doesn't write any State

```pony
fun ref flush(
  low_watermark: U64 val)
: None val
```
#### Parameters

*   low_watermark: [U64](builtin-U64) val

#### Returns

* [None](builtin-None) val

---

### bookkeeping

Process envelopes and keep track of things


```pony
fun ref bookkeeping(
  route_id: U64 val,
  seq_id: U64 val)
: None val
```
#### Parameters

*   route_id: [U64](builtin-U64) val
*   seq_id: [U64](builtin-U64) val

#### Returns

* [None](builtin-None) val

---

### route_to

```pony
fun ref route_to(
  c: Consumer tag)
: (Route ref | None val)
```
#### Parameters

*   c: [Consumer](wallaroo-core-common-Consumer) tag

#### Returns

* ([Route](wallaroo-core-routing-Route) ref | [None](builtin-None) val)

---

### next_sequence_id

```pony
fun ref next_sequence_id()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### current_sequence_id

```pony
fun ref current_sequence_id()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

## Private Functions

### _ack_data_connect

```pony
fun box _ack_data_connect()
: None val
```

#### Returns

* [None](builtin-None) val

---

### _inform_boundary_to_send_normal_messages

```pony
fun box _inform_boundary_to_send_normal_messages()
: None val
```

#### Returns

* [None](builtin-None) val

---

### _write_on_conn

```pony
fun box _write_on_conn(
  data: Array[(String val | Array[U8 val] val)] val)
: None val
```
#### Parameters

*   data: [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val

#### Returns

* [None](builtin-None) val

---

### _acker

```pony
fun ref _acker()
: Acker ref
```

#### Returns

* [Acker](wallaroo-ent-watermarking-Acker) ref

---

### _request_ack

```pony
fun ref _request_ack()
: None val
```

#### Returns

* [None](builtin-None) val

---

### _maybe_ack

```pony
fun ref _maybe_ack()
: None val
```

#### Returns

* [None](builtin-None) val

---

### _ack_latest

```pony
fun ref _ack_latest()
: None val
```

#### Returns

* [None](builtin-None) val

---

### _update_watermark

```pony
fun ref _update_watermark(
  route_id: U64 val,
  seq_id: U64 val)
: None val
```
#### Parameters

*   route_id: [U64](builtin-U64) val
*   seq_id: [U64](builtin-U64) val

#### Returns

* [None](builtin-None) val

---

