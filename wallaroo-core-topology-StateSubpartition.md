# StateSubpartition

```pony
trait val StateSubpartition is
  Equatable[StateSubpartition val] ref
```

#### Implements

* [Equatable](builtin-Equatable)\[[StateSubpartition](wallaroo-core-topology-StateSubpartition) val\] ref

---

## Public Functions

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
: PartitionRouter val
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

* [PartitionRouter](wallaroo-core-topology-PartitionRouter) val

---

### update_key\[Key: ([Hashable](collections-Hashable) val & [Equatable](builtin-Equatable)\[Key\] val)\]

```pony
fun box update_key[Key: (Hashable val & Equatable[Key] val)](
  key: Key,
  pa: ProxyAddress val)
: StateSubpartition val ?
```
#### Parameters

*   key: Key
*   pa: [ProxyAddress](wallaroo-core-topology-ProxyAddress) val

#### Returns

* [StateSubpartition](wallaroo-core-topology-StateSubpartition) val ?

---

### runner_builder

```pony
fun box runner_builder()
: RunnerBuilder val
```

#### Returns

* [RunnerBuilder](wallaroo-core-topology-RunnerBuilder) val

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

