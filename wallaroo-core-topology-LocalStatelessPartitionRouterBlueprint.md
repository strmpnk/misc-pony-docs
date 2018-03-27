# LocalStatelessPartitionRouterBlueprint

```pony
class val LocalStatelessPartitionRouterBlueprint is
  StatelessPartitionRouterBlueprint val
```

#### Implements

* [StatelessPartitionRouterBlueprint](wallaroo-core-topology-StatelessPartitionRouterBlueprint) val

---

## Constructors

### create

```pony
new val create(
  p_id: U128 val,
  s_ids: HashMap[U64 val, U128 val, HashEq[U64 val] val] val,
  partition_addresses: HashMap[U64 val, ProxyAddress val, HashEq[U64 val] val] val,
  steps_per_worker: USize val)
: LocalStatelessPartitionRouterBlueprint val^
```
#### Parameters

*   p_id: [U128](builtin-U128) val
*   s_ids: [HashMap](collections-HashMap)\[[U64](builtin-U64) val, [U128](builtin-U128) val, [HashEq](collections-HashEq)\[[U64](builtin-U64) val\] val\] val
*   partition_addresses: [HashMap](collections-HashMap)\[[U64](builtin-U64) val, [ProxyAddress](wallaroo-core-topology-ProxyAddress) val, [HashEq](collections-HashEq)\[[U64](builtin-U64) val\] val\] val
*   steps_per_worker: [USize](builtin-USize) val

#### Returns

* [LocalStatelessPartitionRouterBlueprint](wallaroo-core-topology-LocalStatelessPartitionRouterBlueprint) val^

---

## Public Functions

### build_router

```pony
fun box build_router(
  worker_name: String val,
  outgoing_boundaries: HashMap[String val, OutgoingBoundary tag, HashEq[String val] val] val,
  auth: AmbientAuth val)
: StatelessPartitionRouter val
```
#### Parameters

*   worker_name: [String](builtin-String) val
*   outgoing_boundaries: [HashMap](collections-HashMap)\[[String](builtin-String) val, [OutgoingBoundary](wallaroo-core-boundary-OutgoingBoundary) tag, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val
*   auth: [AmbientAuth](builtin-AmbientAuth) val

#### Returns

* [StatelessPartitionRouter](wallaroo-core-topology-StatelessPartitionRouter) val

---

