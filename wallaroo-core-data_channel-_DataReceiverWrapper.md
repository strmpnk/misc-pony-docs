# _DataReceiverWrapper

```pony
trait ref _DataReceiverWrapper
```

## Public Functions

### data_connect

```pony
fun box data_connect(
  sender_step_id: U128 val,
  conn: DataChannel tag)
: None val
```
#### Parameters

*   sender_step_id: [U128](builtin-U128) val
*   conn: [DataChannel](wallaroo-core-data_channel-DataChannel) tag

#### Returns

* [None](builtin-None) val

---

### received

```pony
fun box received(
  d: DeliveryMsg val,
  pipeline_time_spent: U64 val,
  seq_id: U64 val,
  latest_ts: U64 val,
  metrics_id: U16 val,
  worker_ingress_ts: U64 val)
: None val
```
#### Parameters

*   d: [DeliveryMsg](wallaroo-core-messages-DeliveryMsg) val
*   pipeline_time_spent: [U64](builtin-U64) val
*   seq_id: [U64](builtin-U64) val
*   latest_ts: [U64](builtin-U64) val
*   metrics_id: [U16](builtin-U16) val
*   worker_ingress_ts: [U64](builtin-U64) val

#### Returns

* [None](builtin-None) val

---

### replay_received

```pony
fun box replay_received(
  r: ReplayableDeliveryMsg val,
  pipeline_time_spent: U64 val,
  seq_id: U64 val,
  latest_ts: U64 val,
  metrics_id: U16 val,
  worker_ingress_ts: U64 val)
: None val
```
#### Parameters

*   r: [ReplayableDeliveryMsg](wallaroo-core-messages-ReplayableDeliveryMsg) val
*   pipeline_time_spent: [U64](builtin-U64) val
*   seq_id: [U64](builtin-U64) val
*   latest_ts: [U64](builtin-U64) val
*   metrics_id: [U16](builtin-U16) val
*   worker_ingress_ts: [U64](builtin-U64) val

#### Returns

* [None](builtin-None) val

---

