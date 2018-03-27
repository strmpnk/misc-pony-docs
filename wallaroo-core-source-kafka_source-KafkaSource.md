# KafkaSource\[In: [Any](builtin-Any) val\]

```pony
actor tag KafkaSource[In: Any val] is
  Producer tag,
  KafkaConsumer ref
```

#### Implements

* [Producer](wallaroo-core-common-Producer) tag
* [KafkaConsumer](pony-kafka-KafkaConsumer) ref

---

## Constructors

### create

```pony
new tag create(
  listen: KafkaSourceListener[In] tag,
  notify: KafkaSourceNotify[In] iso,
  routes: Array[Consumer tag] val,
  route_builder: RouteBuilder val,
  outgoing_boundary_builders: HashMap[String val, OutgoingBoundaryBuilder val, HashEq[String val] val] val,
  layout_initializer: LayoutInitializer tag,
  metrics_reporter: MetricsReporter iso,
  topic: String val,
  partition_id: I32 val,
  kafka_client: KafkaClient tag,
  router_registry: RouterRegistry tag)
: KafkaSource[In] tag^
```
#### Parameters

*   listen: [KafkaSourceListener](wallaroo-core-source-kafka_source-KafkaSourceListener)\[In\] tag
*   notify: [KafkaSourceNotify](wallaroo-core-source-kafka_source-KafkaSourceNotify)\[In\] iso
*   routes: [Array](builtin-Array)\[[Consumer](wallaroo-core-common-Consumer) tag\] val
*   route_builder: [RouteBuilder](wallaroo-core-routing-RouteBuilder) val
*   outgoing_boundary_builders: [HashMap](collections-HashMap)\[[String](builtin-String) val, [OutgoingBoundaryBuilder](wallaroo-core-boundary-OutgoingBoundaryBuilder) val, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val
*   layout_initializer: [LayoutInitializer](wallaroo-core-initialization-LayoutInitializer) tag
*   metrics_reporter: [MetricsReporter](wallaroo-core-metrics-MetricsReporter) iso
*   topic: [String](builtin-String) val
*   partition_id: [I32](builtin-I32) val
*   kafka_client: [KafkaClient](pony-kafka-KafkaClient) tag
*   router_registry: [RouterRegistry](wallaroo-ent-router_registry-RouterRegistry) tag

#### Returns

* [KafkaSource](wallaroo-core-source-kafka_source-KafkaSource)\[In\] tag^

---

## Public Behaviours

### update_router

```pony
be update_router(
  router: Router val)
```
#### Parameters

*   router: [Router](wallaroo-core-topology-Router) val

---

### add_boundary_builders

Build a new boundary for each builder that corresponds to a worker we
don't yet have a boundary to. Each KafkaSource has its own
OutgoingBoundary to each worker to allow for higher throughput.


```pony
be add_boundary_builders(
  boundary_builders: HashMap[String val, OutgoingBoundaryBuilder val, HashEq[String val] val] val)
```
#### Parameters

*   boundary_builders: [HashMap](collections-HashMap)\[[String](builtin-String) val, [OutgoingBoundaryBuilder](wallaroo-core-boundary-OutgoingBoundaryBuilder) val, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val

---

### remove_boundary

```pony
be remove_boundary(
  worker: String val)
```
#### Parameters

*   worker: [String](builtin-String) val

---

### reconnect_boundary

```pony
be reconnect_boundary(
  target_worker_name: String val)
```
#### Parameters

*   target_worker_name: [String](builtin-String) val

---

### remove_route_for

```pony
be remove_route_for(
  step: Consumer tag)
```
#### Parameters

*   step: [Consumer](wallaroo-core-common-Consumer) tag

---

### request_ack

```pony
be request_ack()
```

---

### log_flushed

```pony
be log_flushed(
  low_watermark: U64 val)
```
#### Parameters

*   low_watermark: [U64](builtin-U64) val

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

### receive_kafka_message

```pony
be receive_kafka_message(
  value: Array[U8 val] iso,
  key: (Array[U8 val] val | None val),
  msg_metadata: KafkaMessageMetadata val,
  network_received_timestamp: U64 val)
```
#### Parameters

*   value: [Array](builtin-Array)\[[U8](builtin-U8) val\] iso
*   key: ([Array](builtin-Array)\[[U8](builtin-U8) val\] val | [None](builtin-None) val)
*   msg_metadata: [KafkaMessageMetadata](pony-kafka-KafkaMessageMetadata) val
*   network_received_timestamp: [U64](builtin-U64) val

---

### dispose

```pony
be dispose()
```

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

## Public Functions

### flush

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

```pony
fun ref bookkeeping(
  o_route_id: U64 val,
  o_seq_id: U64 val)
: None val
```
#### Parameters

*   o_route_id: [U64](builtin-U64) val
*   o_seq_id: [U64](builtin-U64) val

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

### is_muted

```pony
fun ref is_muted()
: Bool val
```

#### Returns

* [Bool](builtin-Bool) val

---

## Private Functions

### _acker

```pony
fun ref _acker()
: Acker ref
```

#### Returns

* [Acker](wallaroo-ent-watermarking-Acker) ref

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

### _mute

```pony
fun ref _mute()
: None val
```

#### Returns

* [None](builtin-None) val

---

### _unmute

```pony
fun ref _unmute()
: None val
```

#### Returns

* [None](builtin-None) val

---

