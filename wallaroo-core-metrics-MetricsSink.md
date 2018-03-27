# MetricsSink

```pony
interface tag MetricsSink is
  DisposableActor tag
```

#### Implements

* [DisposableActor](builtin-DisposableActor) tag

---

## Public Behaviours

### send_metrics

```pony
be send_metrics(
  metrics: Array[(String val , String val , String val , String val , U16 val , Histogram val , U64 val , U64 val , String val , String val)] val)
```
#### Parameters

*   metrics: [Array](builtin-Array)\[([String](builtin-String) val , [String](builtin-String) val , [String](builtin-String) val , [String](builtin-String) val , [U16](builtin-U16) val , [Histogram](wallaroo-core-metrics-Histogram) val , [U64](builtin-U64) val , [U64](builtin-U64) val , [String](builtin-String) val , [String](builtin-String) val)\] val

---

### writev

```pony
be writev(
  data: ByteSeqIter val)
```
#### Parameters

*   data: [ByteSeqIter](builtin-ByteSeqIter) val

---

### dispose

```pony
be dispose()
```

---

## Public Functions

### set_nodelay

```pony
fun ref set_nodelay(
  state: Bool val)
: None val
```
#### Parameters

*   state: [Bool](builtin-Bool) val

#### Returns

* [None](builtin-None) val

---

