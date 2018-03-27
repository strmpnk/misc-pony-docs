# SourceNotifyBuilder\[In: [Any](builtin-Any) val, SH: [SourceHandler](wallaroo-core-source-SourceHandler)\[In\] val\]

```pony
interface val SourceNotifyBuilder[In: Any val, SH: SourceHandler[In] val]
```

## Public Functions

### apply

```pony
fun box apply(
  pipeline_name: String val,
  env: Env val,
  auth: AmbientAuth val,
  handler: SH,
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
*   handler: SH
*   runner_builder: [RunnerBuilder](wallaroo-core-topology-RunnerBuilder) val
*   router: [Router](wallaroo-core-topology-Router) val
*   metrics_reporter: [MetricsReporter](wallaroo-core-metrics-MetricsReporter) iso
*   event_log: [EventLog](wallaroo-ent-recovery-EventLog) tag
*   target_router: [Router](wallaroo-core-topology-Router) val
*   pre_state_target_ids: [Array](builtin-Array)\[[U128](builtin-U128) val\] val = seq

#### Returns

* [SourceNotify](wallaroo-core-source-SourceNotify) iso^

---

