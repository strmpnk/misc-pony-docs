# KeyedStateSubpartition\[PIn: [Any](builtin-Any) val, Key: ([Hashable](collections-Hashable) val & [Equatable](builtin-Equatable)\[Key\] val), S: [State](wallaroo-core-state-State) ref\]

```pony
class val KeyedStateSubpartition[PIn: Any val, Key: (Hashable val & Equatable[Key] val), S: State ref] is
  StateSubpartition val
```

#### Implements

* [StateSubpartition](wallaroo-core-topology-StateSubpartition) val

---

## Constructors

### create

```pony
new val create(
  state_name': String val,
  partition_addresses': KeyedPartitionAddresses[Key] val,
  id_map': HashMap[Key, U128 val, HashEq[Key] val] val,
  runner_builder': RunnerBuilder val,
  partition_function': PartitionFunction[PIn, Key] val,
  pipeline_name': String val)
: KeyedStateSubpartition[PIn, Key, S] val^
```
#### Parameters

*   state_name': [String](builtin-String) val
*   partition_addresses': [KeyedPartitionAddresses](wallaroo-core-topology-KeyedPartitionAddresses)\[Key\] val
*   id_map': [HashMap](collections-HashMap)\[Key, [U128](builtin-U128) val, [HashEq](collections-HashEq)\[Key\] val\] val
*   runner_builder': [RunnerBuilder](wallaroo-core-topology-RunnerBuilder) val
*   partition_function': [PartitionFunction](wallaroo-core-topology-PartitionFunction)\[PIn, Key\] val
*   pipeline_name': [String](builtin-String) val

#### Returns

* [KeyedStateSubpartition](wallaroo-core-topology-KeyedStateSubpartition)\[PIn, Key, S\] val^

---

## Public Functions

### runner_builder

```pony
fun box runner_builder()
: RunnerBuilder val
```

#### Returns

* [RunnerBuilder](wallaroo-core-topology-RunnerBuilder) val

---

### build

```pony
fun box build(
  app_name: String val,
  worker_name: String val,
  metrics_conn: MetricsSink tag,
  auth: AmbientAuth val,
  event_log: EventLog tag,
  recovery_replayer: RecoveryReplayer tag,
  outgoing_boundaries: HashMap[String val, OutgoingBoundary tag, HashEq[String val] val] val,
  initializables: HashSet[Initializable tag, HashIs[Initializable tag] val] ref,
  data_routes: HashMap[U128 val, Consumer tag, HashEq[U128 val] val] ref)
: LocalPartitionRouter[PIn, Key, S] val
```
#### Parameters

*   app_name: [String](builtin-String) val
*   worker_name: [String](builtin-String) val
*   metrics_conn: [MetricsSink](wallaroo-core-metrics-MetricsSink) tag
*   auth: [AmbientAuth](builtin-AmbientAuth) val
*   event_log: [EventLog](wallaroo-ent-recovery-EventLog) tag
*   recovery_replayer: [RecoveryReplayer](wallaroo-ent-recovery-RecoveryReplayer) tag
*   outgoing_boundaries: [HashMap](collections-HashMap)\[[String](builtin-String) val, [OutgoingBoundary](wallaroo-core-boundary-OutgoingBoundary) tag, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val
*   initializables: [HashSet](collections-HashSet)\[[Initializable](wallaroo-core-common-Initializable) tag, [HashIs](collections-HashIs)\[[Initializable](wallaroo-core-common-Initializable) tag\] val\] ref
*   data_routes: [HashMap](collections-HashMap)\[[U128](builtin-U128) val, [Consumer](wallaroo-core-common-Consumer) tag, [HashEq](collections-HashEq)\[[U128](builtin-U128) val\] val\] ref

#### Returns

* [LocalPartitionRouter](wallaroo-core-topology-LocalPartitionRouter)\[PIn, Key, S\] val

---

### update_key\[K: ([Hashable](collections-Hashable) val & [Equatable](builtin-Equatable)\[K\] val)\]

```pony
fun box update_key[K: (Hashable val & Equatable[K] val)](
  k: K,
  pa: ProxyAddress val)
: StateSubpartition val ?
```
#### Parameters

*   k: K
*   pa: [ProxyAddress](wallaroo-core-topology-ProxyAddress) val

#### Returns

* [StateSubpartition](wallaroo-core-topology-StateSubpartition) val ?

---

### eq

```pony
fun box eq(
  that: StateSubpartition val)
: Bool val
```
#### Parameters

*   that: [StateSubpartition](wallaroo-core-topology-StateSubpartition) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: StateSubpartition val)
: Bool val
```
#### Parameters

*   that: [StateSubpartition](wallaroo-core-topology-StateSubpartition) val

#### Returns

* [Bool](builtin-Bool) val

---

