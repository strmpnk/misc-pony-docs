# ThroughputBasedClusterGrowthTrigger

ThroughputBasedClusterGrowthTrigger

Triggers a request_new_worker() function call if the throughput
per second exceeds the throughput trigger amount. This is called only
once to avoid new worker overload.


```pony
class ref ThroughputBasedClusterGrowthTrigger is
  MetricsMonitor ref
```

#### Implements

* [MetricsMonitor](wallaroo-core-metrics-MetricsMonitor) ref

---

## Constructors

### create

```pony
new ref create(
  new_worker_requester: NewWorkerRequester tag,
  throughput_trigger_amount: U64 val)
: ThroughputBasedClusterGrowthTrigger ref^
```
#### Parameters

*   new_worker_requester: [NewWorkerRequester](wallaroo-ent-cluster_manager-NewWorkerRequester) tag
*   throughput_trigger_amount: [U64](builtin-U64) val

#### Returns

* [ThroughputBasedClusterGrowthTrigger](wallaroo-ent-cluster_manager-ThroughputBasedClusterGrowthTrigger) ref^

---

## Public fields

* var state: ([_Triggered](wallaroo-ent-cluster_manager-_Triggered) val | [_Untriggered](wallaroo-ent-cluster_manager-_Untriggered) val)

---

## Public Functions

### clone

```pony
fun box clone()
: ThroughputBasedClusterGrowthTrigger iso^
```

#### Returns

* [ThroughputBasedClusterGrowthTrigger](wallaroo-ent-cluster_manager-ThroughputBasedClusterGrowthTrigger) iso^

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

## Private Functions

### _monitor_throughput_for

```pony
fun ref _monitor_throughput_for(
  metrics: Array[(String val , String val , String val , String val , U16 val , Histogram val , U64 val , U64 val , String val , String val)] val)
: None val ?
```
#### Parameters

*   metrics: [Array](builtin-Array)\[([String](builtin-String) val , [String](builtin-String) val , [String](builtin-String) val , [String](builtin-String) val , [U16](builtin-U16) val , [Histogram](wallaroo-core-metrics-Histogram) val , [U64](builtin-U64) val , [U64](builtin-U64) val , [String](builtin-String) val , [String](builtin-String) val)\] val

#### Returns

* [None](builtin-None) val ?

---

### _throughput_per_sec

```pony
fun box _throughput_per_sec(
  metric: (String val , String val , String val , 
    String val , U16 val , Histogram val , 
    U64 val , U64 val , String val , 
    String val))
: F64 val
```
#### Parameters

*   metric: ([String](builtin-String) val , [String](builtin-String) val , [String](builtin-String) val , 
    [String](builtin-String) val , [U16](builtin-U16) val , [Histogram](wallaroo-core-metrics-Histogram) val , 
    [U64](builtin-U64) val , [U64](builtin-U64) val , [String](builtin-String) val , 
    [String](builtin-String) val)

#### Returns

* [F64](builtin-F64) val

---

### _transition_to

```pony
fun ref _transition_to(
  state': (_Triggered val | _Untriggered val))
: None val
```
#### Parameters

*   state': ([_Triggered](wallaroo-ent-cluster_manager-_Triggered) val | [_Untriggered](wallaroo-ent-cluster_manager-_Untriggered) val)

#### Returns

* [None](builtin-None) val

---

