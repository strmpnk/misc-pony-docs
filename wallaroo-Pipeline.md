# Pipeline\[In: [Any](builtin-Any) val, Out: [Any](builtin-Any) val\]

```pony
class ref Pipeline[In: Any val, Out: Any val] is
  BasicPipeline ref
```

#### Implements

* [BasicPipeline](wallaroo-BasicPipeline) ref

---

## Constructors

### create

```pony
new ref create(
  app_name: String val,
  p_id: USize val,
  n: String val,
  sc: SourceConfig[In] val,
  coalescing: Bool val)
: Pipeline[In, Out] ref^
```
#### Parameters

*   app_name: [String](builtin-String) val
*   p_id: [USize](builtin-USize) val
*   n: [String](builtin-String) val
*   sc: [SourceConfig](wallaroo-core-source-SourceConfig)\[In\] val
*   coalescing: [Bool](builtin-Bool) val

#### Returns

* [Pipeline](wallaroo-Pipeline)\[In, Out\] ref^

---

## Public Functions

### add_runner_builder

```pony
fun ref add_runner_builder(
  p: RunnerBuilder val)
: None val
```
#### Parameters

*   p: [RunnerBuilder](wallaroo-core-topology-RunnerBuilder) val

#### Returns

* [None](builtin-None) val

---

### apply

```pony
fun box apply(
  i: USize val)
: RunnerBuilder val ?
```
#### Parameters

*   i: [USize](builtin-USize) val

#### Returns

* [RunnerBuilder](wallaroo-core-topology-RunnerBuilder) val ?

---

### add_sink

```pony
fun ref add_sink(
  sink_builder: SinkBuilder val)
: None val
```
#### Parameters

*   sink_builder: [SinkBuilder](wallaroo-core-sink-SinkBuilder) val

#### Returns

* [None](builtin-None) val

---

### source_id

```pony
fun box source_id()
: USize val
```

#### Returns

* [USize](builtin-USize) val

---

### source_builder

```pony
fun box source_builder()
: SourceBuilderBuilder val ?
```

#### Returns

* [SourceBuilderBuilder](wallaroo-core-source-SourceBuilderBuilder) val ?

---

### source_route_builder

```pony
fun box source_route_builder()
: RouteBuilder val
```

#### Returns

* [RouteBuilder](wallaroo-core-routing-RouteBuilder) val

---

### source_listener_builder_builder

```pony
fun box source_listener_builder_builder()
: SourceListenerBuilderBuilder val
```

#### Returns

* [SourceListenerBuilderBuilder](wallaroo-core-source-SourceListenerBuilderBuilder) val

---

### sink_builders

```pony
fun val sink_builders()
: Array[SinkBuilder val] val
```

#### Returns

* [Array](builtin-Array)\[[SinkBuilder](wallaroo-core-sink-SinkBuilder) val\] val

---

### sink_ids

```pony
fun val sink_ids()
: Array[U128 val] val
```

#### Returns

* [Array](builtin-Array)\[[U128](builtin-U128) val\] val

---

### is_coalesced

```pony
fun box is_coalesced()
: Bool val
```

#### Returns

* [Bool](builtin-Bool) val

---

### size

```pony
fun box size()
: USize val
```

#### Returns

* [USize](builtin-USize) val

---

### name

```pony
fun box name()
: String val
```

#### Returns

* [String](builtin-String) val

---

## Private Functions

### _add_sink_id

```pony
fun ref _add_sink_id()
: None val
```

#### Returns

* [None](builtin-None) val

---

