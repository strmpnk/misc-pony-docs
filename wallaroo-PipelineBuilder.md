# PipelineBuilder\[In: [Any](builtin-Any) val, Out: [Any](builtin-Any) val, Last: [Any](builtin-Any) val\]

```pony
class ref PipelineBuilder[In: Any val, Out: Any val, Last: Any val]
```

## Constructors

### create

```pony
new ref create(
  a: Application ref,
  p: Pipeline[In, Out] ref)
: PipelineBuilder[In, Out, Last] ref^
```
#### Parameters

*   a: [Application](wallaroo-Application) ref
*   p: [Pipeline](wallaroo-Pipeline)\[In, Out\] ref

#### Returns

* [PipelineBuilder](wallaroo-PipelineBuilder)\[In, Out, Last\] ref^

---

## Public Functions

### to\[Next: [Any](builtin-Any) val\]

```pony
fun ref to[Next: Any val](
  comp_builder: ComputationBuilder[Last, Next] val,
  id: U128 val = seq)
: PipelineBuilder[In, Out, Next] ref
```
#### Parameters

*   comp_builder: [ComputationBuilder](wallaroo-core-topology-ComputationBuilder)\[Last, Next\] val
*   id: [U128](builtin-U128) val = seq

#### Returns

* [PipelineBuilder](wallaroo-PipelineBuilder)\[In, Out, Next\] ref

---

### to_parallel\[Next: [Any](builtin-Any) val\]

```pony
fun ref to_parallel[Next: Any val](
  comp_builder: ComputationBuilder[Last, Next] val,
  id: U128 val = seq)
: PipelineBuilder[In, Out, Next] ref
```
#### Parameters

*   comp_builder: [ComputationBuilder](wallaroo-core-topology-ComputationBuilder)\[Last, Next\] val
*   id: [U128](builtin-U128) val = seq

#### Returns

* [PipelineBuilder](wallaroo-PipelineBuilder)\[In, Out, Next\] ref

---

### to_stateful\[Next: [Any](builtin-Any) val, S: [State](wallaroo-core-state-State) ref\]

```pony
fun ref to_stateful[Next: Any val, S: State ref](
  s_comp: StateComputation[Last, Next, S] val,
  s_initializer: StateBuilder[S] val,
  state_name: String val)
: PipelineBuilder[In, Out, Next] ref
```
#### Parameters

*   s_comp: [StateComputation](wallaroo-core-topology-StateComputation)\[Last, Next, S\] val
*   s_initializer: [StateBuilder](wallaroo-core-topology-StateBuilder)\[S\] val
*   state_name: [String](builtin-String) val

#### Returns

* [PipelineBuilder](wallaroo-PipelineBuilder)\[In, Out, Next\] ref

---

### to_state_partition\[PIn: [Any](builtin-Any) val, Key: ([Hashable](collections-Hashable) val & [Equatable](builtin-Equatable)\[Key\]), optional Next: [Any](builtin-Any) val, S: [State](wallaroo-core-state-State) ref\]

```pony
fun ref to_state_partition[PIn: Any val, Key: (Hashable val & Equatable[Key]), optional Next: Any val, S: State ref](
  s_comp: StateComputation[Last, Next, S] val,
  s_initializer: StateBuilder[S] val,
  state_name: String val,
  partition: Partition[PIn, Key] val,
  multi_worker: Bool val = seq)
: PipelineBuilder[In, Out, Next] ref
```
#### Parameters

*   s_comp: [StateComputation](wallaroo-core-topology-StateComputation)\[Last, Next, S\] val
*   s_initializer: [StateBuilder](wallaroo-core-topology-StateBuilder)\[S\] val
*   state_name: [String](builtin-String) val
*   partition: [Partition](wallaroo-core-topology-Partition)\[PIn, Key\] val
*   multi_worker: [Bool](builtin-Bool) val = seq

#### Returns

* [PipelineBuilder](wallaroo-PipelineBuilder)\[In, Out, Next\] ref

---

### done

```pony
fun ref done()
: Application ref
```

#### Returns

* [Application](wallaroo-Application) ref

---

### to_sink

```pony
fun ref to_sink(
  sink_information: SinkConfig[Out] val)
: Application ref
```
#### Parameters

*   sink_information: [SinkConfig](wallaroo-core-sink-SinkConfig)\[Out\] val

#### Returns

* [Application](wallaroo-Application) ref

---

### to_sinks

```pony
fun ref to_sinks(
  sink_configs: Array[SinkConfig[Out] val] box)
: Application ref
```
#### Parameters

*   sink_configs: [Array](builtin-Array)\[[SinkConfig](wallaroo-core-sink-SinkConfig)\[Out\] val\] box

#### Returns

* [Application](wallaroo-Application) ref

---

