# SourceBuilderBuilder

```pony
interface val SourceBuilderBuilder
```

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

