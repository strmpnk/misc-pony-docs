# TypedTCPSourceBuilderBuilder\[In: [Any](builtin-Any) val\]

```pony
class val TypedTCPSourceBuilderBuilder[In: Any val]
```

## Constructors

### create

```pony
new val create(
  app_name: String val,
  name': String val,
  handler: FramedSourceHandler[In] val,
  host': String val,
  service': String val)
: TypedTCPSourceBuilderBuilder[In] val^
```
#### Parameters

*   app_name: [String](builtin-String) val
*   name': [String](builtin-String) val
*   handler: [FramedSourceHandler](wallaroo-core-source-FramedSourceHandler)\[In\] val
*   host': [String](builtin-String) val
*   service': [String](builtin-String) val

#### Returns

* [TypedTCPSourceBuilderBuilder](wallaroo-core-source-tcp_source-TypedTCPSourceBuilderBuilder)\[In\] val^

---

## Public Functions

### name

```pony
fun box name()
: String val
```

#### Returns

* [String](builtin-String) val

---

### apply

```pony
fun box apply(
  runner_builder: RunnerBuilder val,
  router: Router val,
  metrics_conn: MetricsSink tag,
  pre_state_target_ids: Array[U128 val] val = seq,
  worker_name: String val,
  metrics_reporter: MetricsReporter iso)
: SourceBuilder val
```
#### Parameters

*   runner_builder: [RunnerBuilder](wallaroo-core-topology-RunnerBuilder) val
*   router: [Router](wallaroo-core-topology-Router) val
*   metrics_conn: [MetricsSink](wallaroo-core-metrics-MetricsSink) tag
*   pre_state_target_ids: [Array](builtin-Array)\[[U128](builtin-U128) val\] val = seq
*   worker_name: [String](builtin-String) val
*   metrics_reporter: [MetricsReporter](wallaroo-core-metrics-MetricsReporter) iso

#### Returns

* [SourceBuilder](wallaroo-core-source-SourceBuilder) val

---

### host

```pony
fun box host()
: String val
```

#### Returns

* [String](builtin-String) val

---

### service

```pony
fun box service()
: String val
```

#### Returns

* [String](builtin-String) val

---

