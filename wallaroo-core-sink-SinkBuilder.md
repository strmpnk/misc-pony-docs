# SinkBuilder

```pony
interface val SinkBuilder
```

## Public Functions

### apply

```pony
fun box apply(
  reporter: MetricsReporter iso,
  env: Env val)
: (Consumer tag & DisposableActor tag)
```
#### Parameters

*   reporter: [MetricsReporter](wallaroo-core-metrics-MetricsReporter) iso
*   env: [Env](builtin-Env) val

#### Returns

* ([Consumer](wallaroo-core-common-Consumer) tag & [DisposableActor](builtin-DisposableActor) tag)

---

