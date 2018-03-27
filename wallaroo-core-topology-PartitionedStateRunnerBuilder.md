# PartitionedStateRunnerBuilder\[PIn: [Any](builtin-Any) val, S: [State](wallaroo-core-state-State) ref, Key: ([Hashable](collections-Hashable) val & [Equatable](builtin-Equatable)\[Key\])\]

```pony
class val PartitionedStateRunnerBuilder[PIn: Any val, S: State ref, Key: (Hashable val & Equatable[Key])] is
  PartitionBuilder val,
  RunnerBuilder val
```

#### Implements

* [PartitionBuilder](wallaroo-core-topology-PartitionBuilder) val
* [RunnerBuilder](wallaroo-core-topology-RunnerBuilder) val

---

## Constructors

### create

```pony
new val create(
  pipeline_name: String val,
  state_name': String val,
  step_id_map': HashMap[Key, U128 val, HashEq[Key] val] val,
  partition': Partition[PIn, Key] val,
  state_runner_builder: StateRunnerBuilder[S] val,
  route_builder': RouteBuilder val,
  forward_route_builder': RouteBuilder val,
  id': U128 val = seq,
  multi_worker: Bool val = seq)
: PartitionedStateRunnerBuilder[PIn, S, Key] val^
```
#### Parameters

*   pipeline_name: [String](builtin-String) val
*   state_name': [String](builtin-String) val
*   step_id_map': [HashMap](collections-HashMap)\[Key, [U128](builtin-U128) val, [HashEq](collections-HashEq)\[Key\] val\] val
*   partition': [Partition](wallaroo-core-topology-Partition)\[PIn, Key\] val
*   state_runner_builder: [StateRunnerBuilder](wallaroo-core-topology-StateRunnerBuilder)\[S\] val
*   route_builder': [RouteBuilder](wallaroo-core-routing-RouteBuilder) val
*   forward_route_builder': [RouteBuilder](wallaroo-core-routing-RouteBuilder) val
*   id': [U128](builtin-U128) val = seq
*   multi_worker: [Bool](builtin-Bool) val = seq

#### Returns

* [PartitionedStateRunnerBuilder](wallaroo-core-topology-PartitionedStateRunnerBuilder)\[PIn, S, Key\] val^

---

## Public Functions

### apply

```pony
fun box apply(
  event_log: EventLog tag,
  auth: AmbientAuth val,
  next_runner: (Runner iso | None val) = seq,
  router: (Router val | None val) = seq,
  pre_state_target_ids': Array[U128 val] val = seq)
: Runner iso^
```
#### Parameters

*   event_log: [EventLog](wallaroo-ent-recovery-EventLog) tag
*   auth: [AmbientAuth](builtin-AmbientAuth) val
*   next_runner: ([Runner](wallaroo-core-topology-Runner) iso | [None](builtin-None) val) = seq
*   router: ([Router](wallaroo-core-topology-Router) val | [None](builtin-None) val) = seq
*   pre_state_target_ids': [Array](builtin-Array)\[[U128](builtin-U128) val\] val = seq

#### Returns

* [Runner](wallaroo-core-topology-Runner) iso^

---

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

### is_stateful

```pony
fun box is_stateful()
: Bool val
```

#### Returns

* [Bool](builtin-Bool) val

---

### id

```pony
fun box id()
: U128 val
```

#### Returns

* [U128](builtin-U128) val

---

### step_id_map

```pony
fun box step_id_map()
: HashMap[Key, U128 val, HashEq[Key] val] val
```

#### Returns

* [HashMap](collections-HashMap)\[Key, [U128](builtin-U128) val, [HashEq](collections-HashEq)\[Key\] val\] val

---

### route_builder

```pony
fun box route_builder()
: RouteBuilder val
```

#### Returns

* [RouteBuilder](wallaroo-core-routing-RouteBuilder) val

---

### forward_route_builder

```pony
fun box forward_route_builder()
: RouteBuilder val
```

#### Returns

* [RouteBuilder](wallaroo-core-routing-RouteBuilder) val

---

### is_multi

```pony
fun box is_multi()
: Bool val
```

#### Returns

* [Bool](builtin-Bool) val

---

### state_subpartition

```pony
fun box state_subpartition(
  workers: (String val | Array[String val] val))
: StateSubpartition val
```
#### Parameters

*   workers: ([String](builtin-String) val | [Array](builtin-Array)\[[String](builtin-String) val\] val)

#### Returns

* [StateSubpartition](wallaroo-core-topology-StateSubpartition) val

---

### partition_addresses

```pony
fun box partition_addresses(
  workers: (String val | Array[String val] val))
: KeyedPartitionAddresses[Key] val
```
#### Parameters

*   workers: ([String](builtin-String) val | [Array](builtin-Array)\[[String](builtin-String) val\] val)

#### Returns

* [KeyedPartitionAddresses](wallaroo-core-topology-KeyedPartitionAddresses)\[Key\] val

---

### is_prestate

```pony
fun box is_prestate()
: Bool val
```

#### Returns

* [Bool](builtin-Bool) val

---

### is_stateless_parallel

```pony
fun box is_stateless_parallel()
: Bool val
```

#### Returns

* [Bool](builtin-Bool) val

---

### in_route_builder

```pony
fun box in_route_builder()
: (RouteBuilder val | None val)
```

#### Returns

* ([RouteBuilder](wallaroo-core-routing-RouteBuilder) val | [None](builtin-None) val)

---

### clone_router_and_set_input_type

```pony
fun box clone_router_and_set_input_type(
  r: Router val)
: Router val
```
#### Parameters

*   r: [Router](wallaroo-core-topology-Router) val

#### Returns

* [Router](wallaroo-core-topology-Router) val

---

