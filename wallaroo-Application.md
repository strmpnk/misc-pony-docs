# Application

```pony
class ref Application
```

## Constructors

### create

```pony
new ref create(
  name': String val)
: Application ref^
```
#### Parameters

*   name': [String](builtin-String) val

#### Returns

* [Application](wallaroo-Application) ref^

---

## Public fields

* let pipelines: [Array](builtin-Array)\[[BasicPipeline](wallaroo-BasicPipeline) ref\] ref

---

* var sink_count: [USize](builtin-USize) val

---

## Public Functions

### new_pipeline\[In: [Any](builtin-Any) val, Out: [Any](builtin-Any) val\]

```pony
fun ref new_pipeline[In: Any val, Out: Any val](
  pipeline_name: String val,
  source_config: SourceConfig[In] val)
: PipelineBuilder[In, Out, In] ref
```
#### Parameters

*   pipeline_name: [String](builtin-String) val
*   source_config: [SourceConfig](wallaroo-core-source-SourceConfig)\[In\] val

#### Returns

* [PipelineBuilder](wallaroo-PipelineBuilder)\[In, Out, In\] ref

---

### add_pipeline

```pony
fun ref add_pipeline(
  p: BasicPipeline ref)
: None val
```
#### Parameters

*   p: [BasicPipeline](wallaroo-BasicPipeline) ref

#### Returns

* [None](builtin-None) val

---

### add_state_builder

```pony
fun ref add_state_builder(
  state_name: String val,
  state_partition: PartitionBuilder val)
: None val
```
#### Parameters

*   state_name: [String](builtin-String) val
*   state_partition: [PartitionBuilder](wallaroo-core-topology-PartitionBuilder) val

#### Returns

* [None](builtin-None) val

---

### increment_sink_count

```pony
fun ref increment_sink_count()
: None val
```

#### Returns

* [None](builtin-None) val

---

### state_builder

```pony
fun box state_builder(
  state_name: String val)
: PartitionBuilder val ?
```
#### Parameters

*   state_name: [String](builtin-String) val

#### Returns

* [PartitionBuilder](wallaroo-core-topology-PartitionBuilder) val ?

---

### state_builders

```pony
fun box state_builders()
: HashMap[String val, PartitionBuilder val, HashEq[String val] val] val
```

#### Returns

* [HashMap](collections-HashMap)\[[String](builtin-String) val, [PartitionBuilder](wallaroo-core-topology-PartitionBuilder) val, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val

---

### name

```pony
fun box name()
: String val
```

#### Returns

* [String](builtin-String) val

---

### validate

```pony
fun box validate()
: (String val | None val)
```

#### Returns

* ([String](builtin-String) val | [None](builtin-None) val)

---

