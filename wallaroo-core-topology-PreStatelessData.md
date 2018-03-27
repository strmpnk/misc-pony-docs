# PreStatelessData

Unlike PreStateData, this is simply used to create a StatelessPartitionRouter
during local initialization. Whatever step/s come before a stateless
partition do not need to do anything special; they only need the correct
StatelessPartitionRouter.

This is a StepInitializer because it inhabits a node in the local topology
graph, but it does not provide the blueprint for a step.  Instead, it
provides a blueprint for creating the router for the previous step/s in the
graph that have edges into it.


```pony
class val PreStatelessData
```

## Constructors

### create

```pony
new val create(
  pipeline_name': String val,
  step_id': U128 val,
  partition_id_to_worker': HashMap[U64 val, String val, HashEq[U64 val] val] val,
  partition_id_to_step_id': HashMap[U64 val, U128 val, HashEq[U64 val] val] val,
  worker_to_step_id': HashMap[String val, Array[U128 val] val, HashEq[String val] val] val,
  steps_per_worker': USize val)
: PreStatelessData val^
```
#### Parameters

*   pipeline_name': [String](builtin-String) val
*   step_id': [U128](builtin-U128) val
*   partition_id_to_worker': [HashMap](collections-HashMap)\[[U64](builtin-U64) val, [String](builtin-String) val, [HashEq](collections-HashEq)\[[U64](builtin-U64) val\] val\] val
*   partition_id_to_step_id': [HashMap](collections-HashMap)\[[U64](builtin-U64) val, [U128](builtin-U128) val, [HashEq](collections-HashEq)\[[U64](builtin-U64) val\] val\] val
*   worker_to_step_id': [HashMap](collections-HashMap)\[[String](builtin-String) val, [Array](builtin-Array)\[[U128](builtin-U128) val\] val, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val
*   steps_per_worker': [USize](builtin-USize) val

#### Returns

* [PreStatelessData](wallaroo-core-topology-PreStatelessData) val^

---

## Public fields

* let partition_id_to_worker: [HashMap](collections-HashMap)\[[U64](builtin-U64) val, [String](builtin-String) val, [HashEq](collections-HashEq)\[[U64](builtin-U64) val\] val\] val

---

* let partition_id_to_step_id: [HashMap](collections-HashMap)\[[U64](builtin-U64) val, [U128](builtin-U128) val, [HashEq](collections-HashEq)\[[U64](builtin-U64) val\] val\] val

---

* let worker_to_step_id: [HashMap](collections-HashMap)\[[String](builtin-String) val, [Array](builtin-Array)\[[U128](builtin-U128) val\] val, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val

---

* let steps_per_worker: [USize](builtin-USize) val

---

## Public Functions

### name

```pony
fun box name()
: String val
```

#### Returns

* [String](builtin-String) val

---

### state_name

```pony
fun box state_name()
: String val
```

#### Returns

* [String](builtin-String) val

---

### pipeline_name

```pony
fun box pipeline_name()
: String val
```

#### Returns

* [String](builtin-String) val

---

### id

```pony
fun box id()
: U128 val
```

#### Returns

* [U128](builtin-U128) val

---

### pre_state_target_ids

```pony
fun box pre_state_target_ids()
: Array[U128 val] val
```

#### Returns

* [Array](builtin-Array)\[[U128](builtin-U128) val\] val

---

### is_prestate

```pony
fun box is_prestate()
: Bool val
```

#### Returns

* [Bool](builtin-Bool) val

---

### is_stateful

```pony
fun box is_stateful()
: Bool val
```

#### Returns

* [Bool](builtin-Bool) val

---

### is_partitioned

```pony
fun box is_partitioned()
: Bool val
```

#### Returns

* [Bool](builtin-Bool) val

---

### forward_route_builder

```pony
fun box forward_route_builder()
: RouteBuilder val
```

#### Returns

* [RouteBuilder](wallaroo-core-routing-RouteBuilder) val

---

### clone_router_and_set_input_type

```pony
fun box clone_router_and_set_input_type(
  r: Router val,
  dr: (Router val | None val) = seq)
: Router val
```
#### Parameters

*   r: [Router](wallaroo-core-topology-Router) val
*   dr: ([Router](wallaroo-core-topology-Router) val | [None](builtin-None) val) = seq

#### Returns

* [Router](wallaroo-core-topology-Router) val

---

