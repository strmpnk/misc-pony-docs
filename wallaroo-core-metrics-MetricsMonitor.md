# MetricsMonitor

MetricsMonitor

Interface for hooking into a MetricsReporter and being able to
monitor metrics via on_send prior to a send_metrics() call.


```pony
interface ref MetricsMonitor
```

## Public Functions

### clone

```pony
fun box clone()
: MetricsMonitor iso^
```

#### Returns

* [MetricsMonitor](wallaroo-core-metrics-MetricsMonitor) iso^

---

### on_send

Hook for monitoring metrics prior to send_metrics() call.


```pony
fun ref on_send(
  metrics: Array[(String val , String val , String val , String val , U16 val , Histogram val , U64 val , U64 val , String val , String val)] val)
: None val
```
#### Parameters

*   metrics: [Array](builtin-Array)\[([String](builtin-String) val , [String](builtin-String) val , [String](builtin-String) val , [String](builtin-String) val , [U16](builtin-U16) val , [Histogram](wallaroo-core-metrics-Histogram) val , [U64](builtin-U64) val , [U64](builtin-U64) val , [String](builtin-String) val , [String](builtin-String) val)\] val

#### Returns

* [None](builtin-None) val

---

