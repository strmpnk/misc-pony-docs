# BasicSourceBuilder\[In: [Any](builtin-Any) val, SH: [SourceHandler](wallaroo-core-source-SourceHandler)\[In\] val\]

```pony
class val BasicSourceBuilder[In: Any val, SH: SourceHandler[In] val] is
  SourceBuilder val
```

#### Implements

* [SourceBuilder](wallaroo-core-source-SourceBuilder) val

---

## Constructors

### create

```pony
new val create(
  app_name: String val,
  worker_name: String val,
  name': String val,
  runner_builder: RunnerBuilder val,
  handler: SH,
  router: Router val,
  metrics_conn: MetricsSink tag,
  pre_state_target_ids: Array[U128 val] val = seq,
  metrics_reporter: MetricsReporter iso,
  source_notify_builder: SourceNotifyBuilder[In, SH] val)
: BasicSourceBuilder[In, SH] val^
```
#### Parameters

*   app_name: [String](builtin-String) val
*   worker_name: [String](builtin-String) val
*   name': [String](builtin-String) val
*   runner_builder: [RunnerBuilder](wallaroo-core-topology-RunnerBuilder) val
*   handler: SH
*   router: [Router](wallaroo-core-topology-Router) val
*   metrics_conn: [MetricsSink](wallaroo-core-metrics-MetricsSink) tag
*   pre_state_target_ids: [Array](builtin-Array)\[[U128](builtin-U128) val\] val = seq
*   metrics_reporter: [MetricsReporter](wallaroo-core-metrics-MetricsReporter) iso
*   source_notify_builder: [SourceNotifyBuilder](wallaroo-core-source-SourceNotifyBuilder)\[In, SH\] val

#### Returns

* [BasicSourceBuilder](wallaroo-core-source-BasicSourceBuilder)\[In, SH\] val^

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
  event_log: EventLog tag,
  auth: AmbientAuth val,
  target_router: Router val,
  env: Env val)
: SourceNotify iso^
```
#### Parameters

*   event_log: [EventLog](wallaroo-ent-recovery-EventLog) tag
*   auth: [AmbientAuth](builtin-AmbientAuth) val
*   target_router: [Router](wallaroo-core-topology-Router) val
*   env: [Env](builtin-Env) val

#### Returns

* [SourceNotify](wallaroo-core-source-SourceNotify) iso^

---

### update_router

```pony
fun val update_router(
  router: Router val)
: SourceBuilder val
```
#### Parameters

*   router: [Router](wallaroo-core-topology-Router) val

#### Returns

* [SourceBuilder](wallaroo-core-source-SourceBuilder) val

---

