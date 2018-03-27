# _MetricsReporter

```pony
class ref _MetricsReporter
```

## Constructors

### create

```pony
new ref create(
  output_to': MetricsSink tag,
  app_name': String val,
  worker_name': String val,
  pipeline': String val,
  metric_name': String val,
  id': U16 val,
  prefix': String val,
  category': (ComputationCategory val | StartToEndCategory val | NodeIngressEgressCategory val | 
    PipelineIngestionCategory val))
: _MetricsReporter ref^
```
#### Parameters

*   output_to': [MetricsSink](wallaroo-core-metrics-MetricsSink) tag
*   app_name': [String](builtin-String) val
*   worker_name': [String](builtin-String) val
*   pipeline': [String](builtin-String) val
*   metric_name': [String](builtin-String) val
*   id': [U16](builtin-U16) val
*   prefix': [String](builtin-String) val
*   category': ([ComputationCategory](wallaroo-core-metrics-ComputationCategory) val | [StartToEndCategory](wallaroo-core-metrics-StartToEndCategory) val | [NodeIngressEgressCategory](wallaroo-core-metrics-NodeIngressEgressCategory) val | 
    [PipelineIngestionCategory](wallaroo-core-metrics-PipelineIngestionCategory) val)

#### Returns

* [_MetricsReporter](wallaroo-core-metrics-_MetricsReporter) ref^

---

## Public Functions

### report

```pony
fun ref report(
  duration: U64 val)
: None val
```
#### Parameters

*   duration: [U64](builtin-U64) val

#### Returns

* [None](builtin-None) val

---

### topic

```pony
fun ref topic()
: String val
```

#### Returns

* [String](builtin-String) val

---

### metric_name

```pony
fun ref metric_name()
: String val
```

#### Returns

* [String](builtin-String) val

---

### pipeline

```pony
fun ref pipeline()
: String val
```

#### Returns

* [String](builtin-String) val

---

### worker_name

```pony
fun ref worker_name()
: String val
```

#### Returns

* [String](builtin-String) val

---

### id

```pony
fun ref id()
: U16 val
```

#### Returns

* [U16](builtin-U16) val

---

### category

```pony
fun ref category()
: String val
```

#### Returns

* [String](builtin-String) val

---

### reset_histogram

```pony
fun ref reset_histogram()
: Histogram iso^
```

#### Returns

* [Histogram](wallaroo-core-metrics-Histogram) iso^

---

