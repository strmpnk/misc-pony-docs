# RouteBuilder

```pony
trait val RouteBuilder
```

## Public Functions

### apply

```pony
fun box apply(
  step: Producer ref,
  consumer: Consumer tag,
  metrics_reporter: MetricsReporter ref)
: Route ref
```
#### Parameters

*   step: [Producer](wallaroo-core-common-Producer) ref
*   consumer: [Consumer](wallaroo-core-common-Consumer) tag
*   metrics_reporter: [MetricsReporter](wallaroo-core-metrics-MetricsReporter) ref

#### Returns

* [Route](wallaroo-core-routing-Route) ref

---

