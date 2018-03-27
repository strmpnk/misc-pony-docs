# DefaultMetricsMonitor

```pony
class ref DefaultMetricsMonitor is
  MetricsMonitor ref
```

#### Implements

* [MetricsMonitor](wallaroo-core-metrics-MetricsMonitor) ref

---

## Constructors

### create

```pony
new iso create()
: DefaultMetricsMonitor iso^
```

#### Returns

* [DefaultMetricsMonitor](wallaroo-core-metrics-DefaultMetricsMonitor) iso^

---

## Public Functions

### clone

```pony
fun box clone()
: DefaultMetricsMonitor iso^
```

#### Returns

* [DefaultMetricsMonitor](wallaroo-core-metrics-DefaultMetricsMonitor) iso^

---

### on_send

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

