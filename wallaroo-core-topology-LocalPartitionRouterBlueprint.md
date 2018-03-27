# LocalPartitionRouterBlueprint\[In: [Any](builtin-Any) val, Key: ([Hashable](collections-Hashable) val & [Equatable](builtin-Equatable)\[Key\] val), S: [State](wallaroo-core-state-State) ref\]

```pony
class val LocalPartitionRouterBlueprint[In: Any val, Key: (Hashable val & Equatable[Key] val), S: State ref] is
  PartitionRouterBlueprint val
```

#### Implements

* [PartitionRouterBlueprint](wallaroo-core-topology-PartitionRouterBlueprint) val

---

## Constructors

### create

```pony
new val create(
  state_name: String val,
  s_ids: HashMap[Key, U128 val, HashEq[Key] val] val,
  partition_addresses: HashMap[Key, ProxyAddress val, HashEq[Key] val] val,
  partition_function: PartitionFunction[In, Key] val)
: LocalPartitionRouterBlueprint[In, Key, S] val^
```
#### Parameters

*   state_name: [String](builtin-String) val
*   s_ids: [HashMap](collections-HashMap)\[Key, [U128](builtin-U128) val, [HashEq](collections-HashEq)\[Key\] val\] val
*   partition_addresses: [HashMap](collections-HashMap)\[Key, [ProxyAddress](wallaroo-core-topology-ProxyAddress) val, [HashEq](collections-HashEq)\[Key\] val\] val
*   partition_function: [PartitionFunction](wallaroo-core-topology-PartitionFunction)\[In, Key\] val

#### Returns

* [LocalPartitionRouterBlueprint](wallaroo-core-topology-LocalPartitionRouterBlueprint)\[In, Key, S\] val^

---

## Public Functions

### build_router

```pony
fun box build_router(
  worker_name: String val,
  outgoing_boundaries: HashMap[String val, OutgoingBoundary tag, HashEq[String val] val] val,
  auth: AmbientAuth val)
: PartitionRouter val
```
#### Parameters

*   worker_name: [String](builtin-String) val
*   outgoing_boundaries: [HashMap](collections-HashMap)\[[String](builtin-String) val, [OutgoingBoundary](wallaroo-core-boundary-OutgoingBoundary) tag, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val
*   auth: [AmbientAuth](builtin-AmbientAuth) val

#### Returns

* [PartitionRouter](wallaroo-core-topology-PartitionRouter) val

---

