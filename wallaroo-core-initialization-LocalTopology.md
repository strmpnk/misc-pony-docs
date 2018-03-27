# LocalTopology

```pony
class val LocalTopology
```

## Constructors

### create

```pony
new val create(
  name': String val,
  worker_name': String val,
  graph': Dag[(StepBuilder val | SourceData val | EgressBuilder val | PreStatelessData val)] val,
  step_map': HashMap[U128 val, (ProxyAddress val | U128 val), HashEq[U128 val] val] val,
  state_builders': HashMap[String val, StateSubpartition val, HashEq[String val] val] val,
  pre_state_data': Array[PreStateData val] val,
  proxy_ids': HashMap[String val, U128 val, HashEq[String val] val] val,
  worker_names': Array[String val] val,
  non_shrinkable': HashSet[String val, HashIs[String val] val] val)
: LocalTopology val^
```
#### Parameters

*   name': [String](builtin-String) val
*   worker_name': [String](builtin-String) val
*   graph': [Dag](wallaroo_labs-dag-Dag)\[([StepBuilder](wallaroo-core-topology-StepBuilder) val | [SourceData](wallaroo-core-topology-SourceData) val | [EgressBuilder](wallaroo-core-topology-EgressBuilder) val | [PreStatelessData](wallaroo-core-topology-PreStatelessData) val)\] val
*   step_map': [HashMap](collections-HashMap)\[[U128](builtin-U128) val, ([ProxyAddress](wallaroo-core-topology-ProxyAddress) val | [U128](builtin-U128) val), [HashEq](collections-HashEq)\[[U128](builtin-U128) val\] val\] val
*   state_builders': [HashMap](collections-HashMap)\[[String](builtin-String) val, [StateSubpartition](wallaroo-core-topology-StateSubpartition) val, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val
*   pre_state_data': [Array](builtin-Array)\[[PreStateData](wallaroo-core-topology-PreStateData) val\] val
*   proxy_ids': [HashMap](collections-HashMap)\[[String](builtin-String) val, [U128](builtin-U128) val, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val
*   worker_names': [Array](builtin-Array)\[[String](builtin-String) val\] val
*   non_shrinkable': [HashSet](collections-HashSet)\[[String](builtin-String) val, [HashIs](collections-HashIs)\[[String](builtin-String) val\] val\] val

#### Returns

* [LocalTopology](wallaroo-core-initialization-LocalTopology) val^

---

## Public fields

* let worker_names: [Array](builtin-Array)\[[String](builtin-String) val\] val

---

* let non_shrinkable: [HashSet](collections-HashSet)\[[String](builtin-String) val, [HashIs](collections-HashIs)\[[String](builtin-String) val\] val\] val

---

## Public Functions

### state_builders

```pony
fun box state_builders()
: HashMap[String val, StateSubpartition val, HashEq[String val] val] val
```

#### Returns

* [HashMap](collections-HashMap)\[[String](builtin-String) val, [StateSubpartition](wallaroo-core-topology-StateSubpartition) val, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val

---

### update_state_map

```pony
fun box update_state_map(
  state_name: String val,
  state_map: HashMap[String val, Router val, HashEq[String val] val] ref,
  metrics_conn: MetricsSink tag,
  event_log: EventLog tag,
  recovery_replayer: RecoveryReplayer tag,
  auth: AmbientAuth val,
  outgoing_boundaries: HashMap[String val, OutgoingBoundary tag, HashEq[String val] val] val,
  initializables: HashSet[Initializable tag, HashIs[Initializable tag] val] ref,
  data_routes: HashMap[U128 val, Consumer tag, HashEq[U128 val] val] ref)
: None val ?
```
#### Parameters

*   state_name: [String](builtin-String) val
*   state_map: [HashMap](collections-HashMap)\[[String](builtin-String) val, [Router](wallaroo-core-topology-Router) val, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] ref
*   metrics_conn: [MetricsSink](wallaroo-core-metrics-MetricsSink) tag
*   event_log: [EventLog](wallaroo-ent-recovery-EventLog) tag
*   recovery_replayer: [RecoveryReplayer](wallaroo-ent-recovery-RecoveryReplayer) tag
*   auth: [AmbientAuth](builtin-AmbientAuth) val
*   outgoing_boundaries: [HashMap](collections-HashMap)\[[String](builtin-String) val, [OutgoingBoundary](wallaroo-core-boundary-OutgoingBoundary) tag, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val
*   initializables: [HashSet](collections-HashSet)\[[Initializable](wallaroo-core-common-Initializable) tag, [HashIs](collections-HashIs)\[[Initializable](wallaroo-core-common-Initializable) tag\] val\] ref
*   data_routes: [HashMap](collections-HashMap)\[[U128](builtin-U128) val, [Consumer](wallaroo-core-common-Consumer) tag, [HashEq](collections-HashEq)\[[U128](builtin-U128) val\] val\] ref

#### Returns

* [None](builtin-None) val ?

---

### graph

```pony
fun box graph()
: Dag[(StepBuilder val | SourceData val | EgressBuilder val | PreStatelessData val)] val
```

#### Returns

* [Dag](wallaroo_labs-dag-Dag)\[([StepBuilder](wallaroo-core-topology-StepBuilder) val | [SourceData](wallaroo-core-topology-SourceData) val | [EgressBuilder](wallaroo-core-topology-EgressBuilder) val | [PreStatelessData](wallaroo-core-topology-PreStatelessData) val)\] val

---

### pre_state_data

```pony
fun box pre_state_data()
: Array[PreStateData val] val
```

#### Returns

* [Array](builtin-Array)\[[PreStateData](wallaroo-core-topology-PreStateData) val\] val

---

### step_map

```pony
fun box step_map()
: HashMap[U128 val, (ProxyAddress val | U128 val), HashEq[U128 val] val] val
```

#### Returns

* [HashMap](collections-HashMap)\[[U128](builtin-U128) val, ([ProxyAddress](wallaroo-core-topology-ProxyAddress) val | [U128](builtin-U128) val), [HashEq](collections-HashEq)\[[U128](builtin-U128) val\] val\] val

---

### name

```pony
fun box name()
: String val
```

#### Returns

* [String](builtin-String) val

---

### worker_name

```pony
fun box worker_name()
: String val
```

#### Returns

* [String](builtin-String) val

---

### is_empty

```pony
fun box is_empty()
: Bool val
```

#### Returns

* [Bool](builtin-Bool) val

---

### proxy_ids

```pony
fun box proxy_ids()
: HashMap[String val, U128 val, HashEq[String val] val] val
```

#### Returns

* [HashMap](collections-HashMap)\[[String](builtin-String) val, [U128](builtin-U128) val, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val

---

### update_proxy_address_for_state_key\[Key: ([Hashable](collections-Hashable) val & [Equatable](builtin-Equatable)\[Key\] val)\]

```pony
fun box update_proxy_address_for_state_key[Key: (Hashable val & Equatable[Key] val)](
  state_name: String val,
  key: Key,
  pa: ProxyAddress val)
: LocalTopology val ?
```
#### Parameters

*   state_name: [String](builtin-String) val
*   key: Key
*   pa: [ProxyAddress](wallaroo-core-topology-ProxyAddress) val

#### Returns

* [LocalTopology](wallaroo-core-initialization-LocalTopology) val ?

---

### add_worker_name

```pony
fun val add_worker_name(
  w: String val)
: LocalTopology val
```
#### Parameters

*   w: [String](builtin-String) val

#### Returns

* [LocalTopology](wallaroo-core-initialization-LocalTopology) val

---

### remove_worker_names

```pony
fun val remove_worker_names(
  ws: Array[String val] val)
: LocalTopology val
```
#### Parameters

*   ws: [Array](builtin-Array)\[[String](builtin-String) val\] val

#### Returns

* [LocalTopology](wallaroo-core-initialization-LocalTopology) val

---

### for_new_worker

```pony
fun val for_new_worker(
  new_worker: String val)
: LocalTopology val ?
```
#### Parameters

*   new_worker: [String](builtin-String) val

#### Returns

* [LocalTopology](wallaroo-core-initialization-LocalTopology) val ?

---

### eq

```pony
fun box eq(
  that: LocalTopology val)
: Bool val
```
#### Parameters

*   that: [LocalTopology](wallaroo-core-initialization-LocalTopology) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: LocalTopology val)
: Bool val
```
#### Parameters

*   that: [LocalTopology](wallaroo-core-initialization-LocalTopology) val

#### Returns

* [Bool](builtin-Bool) val

---

