# KafkaSourceNotifyBuilder\[In: [Any](builtin-Any) val\]

```pony
primitive val KafkaSourceNotifyBuilder[In: Any val]
```

## Constructors

### create

```pony
new val create()
: KafkaSourceNotifyBuilder[In] val^
```

#### Returns

* [KafkaSourceNotifyBuilder](wallaroo-core-source-kafka_source-KafkaSourceNotifyBuilder)\[In\] val^

---

## Public Functions

### apply

```pony
fun box apply(
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
: SourceNotify iso^
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

* [SourceNotify](wallaroo-core-source-SourceNotify) iso^

---

### eq

```pony
fun box eq(
  that: KafkaSourceNotifyBuilder[In] val)
: Bool val
```
#### Parameters

*   that: [KafkaSourceNotifyBuilder](wallaroo-core-source-kafka_source-KafkaSourceNotifyBuilder)\[In\] val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: KafkaSourceNotifyBuilder[In] val)
: Bool val
```
#### Parameters

*   that: [KafkaSourceNotifyBuilder](wallaroo-core-source-kafka_source-KafkaSourceNotifyBuilder)\[In\] val

#### Returns

* [Bool](builtin-Bool) val

---

