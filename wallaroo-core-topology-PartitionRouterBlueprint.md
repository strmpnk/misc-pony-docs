# PartitionRouterBlueprint

```pony
trait val PartitionRouterBlueprint
```

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

