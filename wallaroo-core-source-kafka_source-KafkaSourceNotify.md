# KafkaSourceNotify\[In: [Any](builtin-Any) val\]

```pony
class ref KafkaSourceNotify[In: Any val]
```

## Constructors

### create

```pony
new iso create(
  pipeline_name: String val,
  env: Env val,
  auth: AmbientAuth val,
  handler: SourceHandler[In] val,
  runner_builder: RunnerBuilder val,
  router: Router val,
  metrics_reporter: MetricsReporter iso,
  event_log: EventLog tag,
  target_router: Router val,
  pre_state_target_ids: Array[U128 val] val = seq)
: KafkaSourceNotify[In] iso^
```
#### Parameters

*   pipeline_name: [String](builtin-String) val
*   env: [Env](builtin-Env) val
*   auth: [AmbientAuth](builtin-AmbientAuth) val
*   handler: [SourceHandler](wallaroo-core-source-SourceHandler)\[In\] val
*   runner_builder: [RunnerBuilder](wallaroo-core-topology-RunnerBuilder) val
*   router: [Router](wallaroo-core-topology-Router) val
*   metrics_reporter: [MetricsReporter](wallaroo-core-metrics-MetricsReporter) iso
*   event_log: [EventLog](wallaroo-ent-recovery-EventLog) tag
*   target_router: [Router](wallaroo-core-topology-Router) val
*   pre_state_target_ids: [Array](builtin-Array)\[[U128](builtin-U128) val\] val = seq

#### Returns

* [KafkaSourceNotify](wallaroo-core-source-kafka_source-KafkaSourceNotify)\[In\] iso^

---

## Public Functions

### routes

```pony
fun box routes()
: Array[Consumer tag] val
```

#### Returns

* [Array](builtin-Array)\[[Consumer](wallaroo-core-common-Consumer) tag\] val

---

### received

```pony
fun ref received(
  src: KafkaSource[In] ref,
  kafka_msg_value: Array[U8 val] iso,
  kafka_msg_key: (Array[U8 val] val | None val),
  kafka_msg_metadata: KafkaMessageMetadata val,
  network_received_timestamp: U64 val)
: None val
```
#### Parameters

*   src: [KafkaSource](wallaroo-core-source-kafka_source-KafkaSource)\[In\] ref
*   kafka_msg_value: [Array](builtin-Array)\[[U8](builtin-U8) val\] iso
*   kafka_msg_key: ([Array](builtin-Array)\[[U8](builtin-U8) val\] val | [None](builtin-None) val)
*   kafka_msg_metadata: [KafkaMessageMetadata](pony-kafka-KafkaMessageMetadata) val
*   network_received_timestamp: [U64](builtin-U64) val

#### Returns

* [None](builtin-None) val

---

### update_router

```pony
fun ref update_router(
  router: Router val)
: None val
```
#### Parameters

*   router: [Router](wallaroo-core-topology-Router) val

#### Returns

* [None](builtin-None) val

---

### update_boundaries

```pony
fun ref update_boundaries(
  obs: HashMap[String val, OutgoingBoundary tag, HashEq[String val] val] box)
: None val
```
#### Parameters

*   obs: [HashMap](collections-HashMap)\[[String](builtin-String) val, [OutgoingBoundary](wallaroo-core-boundary-OutgoingBoundary) tag, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] box

#### Returns

* [None](builtin-None) val

---

