# MetricsReporter

```pony
class ref MetricsReporter
```

## Constructors

### create

```pony
new iso create(
  app_name: String val,
  worker_name: String val,
  metrics_conn: MetricsSink tag,
  period: U64 val = seq,
  metrics_monitor: MetricsMonitor iso = seq)
: MetricsReporter iso^
```
#### Parameters

*   app_name: [String](builtin-String) val
*   worker_name: [String](builtin-String) val
*   metrics_conn: [MetricsSink](wallaroo-core-metrics-MetricsSink) tag
*   period: [U64](builtin-U64) val = seq
*   metrics_monitor: [MetricsMonitor](wallaroo-core-metrics-MetricsMonitor) iso = seq

#### Returns

* [MetricsReporter](wallaroo-core-metrics-MetricsReporter) iso^

---

## Public Functions

### clone

```pony
fun box clone()
: MetricsReporter iso^
```

#### Returns

* [MetricsReporter](wallaroo-core-metrics-MetricsReporter) iso^

---

### step_metric

```pony
fun ref step_metric(
  pipeline: String val,
  name: String val,
  id: U16 val,
  start_ts: U64 val,
  end_ts: U64 val,
  prefix: String val = seq)
: None val
```
#### Parameters

*   pipeline: [String](builtin-String) val
*   name: [String](builtin-String) val
*   id: [U16](builtin-U16) val
*   start_ts: [U64](builtin-U64) val
*   end_ts: [U64](builtin-U64) val
*   prefix: [String](builtin-String) val = seq

#### Returns

* [None](builtin-None) val

---

### pipeline_ingest

Used to report how many messages are ingested at a source over a given
time frame. Latency is reported as 0 since processing time is not
part of this metric.


```pony
fun ref pipeline_ingest(
  pipeline: String val,
  source_name: String val)
: None val
```
#### Parameters

*   pipeline: [String](builtin-String) val
*   source_name: [String](builtin-String) val

#### Returns

* [None](builtin-None) val

---

### pipeline_metric

```pony
fun ref pipeline_metric(
  source_name: String val,
  time_spent: U64 val)
: None val
```
#### Parameters

*   source_name: [String](builtin-String) val
*   time_spent: [U64](builtin-U64) val

#### Returns

* [None](builtin-None) val

---

### worker_metric

```pony
fun ref worker_metric(
  pipeline_name: String val,
  time_spent: U64 val)
: None val
```
#### Parameters

*   pipeline_name: [String](builtin-String) val
*   time_spent: [U64](builtin-U64) val

#### Returns

* [None](builtin-None) val

---

## Private Functions

### _next_period_endtime

Nanosecond end of the period in which time belongs


```pony
fun ref _next_period_endtime(
  time: U64 val,
  length: U64 val)
: U64 val
```
#### Parameters

*   time: [U64](builtin-U64) val
*   length: [U64](builtin-U64) val

#### Returns

* [U64](builtin-U64) val

---

### _maybe_send_metrics

```pony
fun ref _maybe_send_metrics()
: None val
```

#### Returns

* [None](builtin-None) val

---

