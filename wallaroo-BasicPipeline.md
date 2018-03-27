# BasicPipeline

```pony
trait ref BasicPipeline
```

## Public Functions

### name

```pony
fun box name()
: String val
```

#### Returns

* [String](builtin-String) val

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

### size

```pony
fun box size()
: USize val
```

#### Returns

* [USize](builtin-USize) val

---

