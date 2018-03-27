# DummyConsumer

```pony
actor tag DummyConsumer is
  Consumer tag
```

#### Implements

* [Consumer](wallaroo-core-common-Consumer) tag

---

## Constructors

### create

```pony
new tag create()
: DummyConsumer tag^
```

#### Returns

* [DummyConsumer](wallaroo-core-common-DummyConsumer) tag^

---

## Public Behaviours

### register_producer

```pony
be register_producer(
  producer: Producer tag)
```
#### Parameters

*   producer: [Producer](wallaroo-core-common-Producer) tag

---

### unregister_producer

```pony
be unregister_producer(
  producer: Producer tag)
```
#### Parameters

*   producer: [Producer](wallaroo-core-common-Producer) tag

---

### run\[D: [Any](builtin-Any) val\]

```pony
be run[D: Any val](
  metric_name: String val,
  pipeline_time_spent: U64 val,
  data: D,
  i_producer: Producer tag,
  msg_uid: U128 val,
  frac_ids: (Array[U32 val] val | None val),
  i_seq_id: U64 val,
  i_route_id: U64 val,
  latest_ts: U64 val,
  metrics_id: U16 val,
  worker_ingress_ts: U64 val)
```
#### Parameters

*   metric_name: [String](builtin-String) val
*   pipeline_time_spent: [U64](builtin-U64) val
*   data: D
*   i_producer: [Producer](wallaroo-core-common-Producer) tag
*   msg_uid: [U128](builtin-U128) val
*   frac_ids: ([Array](builtin-Array)\[[U32](builtin-U32) val\] val | [None](builtin-None) val)
*   i_seq_id: [U64](builtin-U64) val
*   i_route_id: [U64](builtin-U64) val
*   latest_ts: [U64](builtin-U64) val
*   metrics_id: [U16](builtin-U16) val
*   worker_ingress_ts: [U64](builtin-U64) val

---

### replay_run\[D: [Any](builtin-Any) val\]

```pony
be replay_run[D: Any val](
  metric_name: String val,
  pipeline_time_spent: U64 val,
  data: D,
  i_producer: Producer tag,
  msg_uid: U128 val,
  frac_ids: (Array[U32 val] val | None val),
  i_seq_id: U64 val,
  i_route_id: U64 val,
  latest_ts: U64 val,
  metrics_id: U16 val,
  worker_ingress_ts: U64 val)
```
#### Parameters

*   metric_name: [String](builtin-String) val
*   pipeline_time_spent: [U64](builtin-U64) val
*   data: D
*   i_producer: [Producer](wallaroo-core-common-Producer) tag
*   msg_uid: [U128](builtin-U128) val
*   frac_ids: ([Array](builtin-Array)\[[U32](builtin-U32) val\] val | [None](builtin-None) val)
*   i_seq_id: [U64](builtin-U64) val
*   i_route_id: [U64](builtin-U64) val
*   latest_ts: [U64](builtin-U64) val
*   metrics_id: [U16](builtin-U16) val
*   worker_ingress_ts: [U64](builtin-U64) val

---

### receive_state

```pony
be receive_state(
  state: (String val | Array[U8 val] val))
```
#### Parameters

*   state: ([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)

---

### request_ack

```pony
be request_ack()
```

---

### application_begin_reporting

```pony
be application_begin_reporting(
  initializer: LocalTopologyInitializer tag)
```
#### Parameters

*   initializer: [LocalTopologyInitializer](wallaroo-core-initialization-LocalTopologyInitializer) tag

---

### application_created

```pony
be application_created(
  initializer: LocalTopologyInitializer tag,
  omni_router: OmniRouter val)
```
#### Parameters

*   initializer: [LocalTopologyInitializer](wallaroo-core-initialization-LocalTopologyInitializer) tag
*   omni_router: [OmniRouter](wallaroo-core-topology-OmniRouter) val

---

### application_initialized

```pony
be application_initialized(
  initializer: LocalTopologyInitializer tag)
```
#### Parameters

*   initializer: [LocalTopologyInitializer](wallaroo-core-initialization-LocalTopologyInitializer) tag

---

### application_ready_to_work

```pony
be application_ready_to_work(
  initializer: LocalTopologyInitializer tag)
```
#### Parameters

*   initializer: [LocalTopologyInitializer](wallaroo-core-initialization-LocalTopologyInitializer) tag

---

