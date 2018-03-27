# OmniRouterBlueprint

```pony
trait val OmniRouterBlueprint
```

## Public Functions

### build_router

```pony
fun box build_router(
  worker_name: String val,
  outgoing_boundaries: HashMap[String val, OutgoingBoundary tag, HashEq[String val] val] val,
  local_sinks: HashMap[U128 val, Consumer tag, HashEq[U128 val] val] val)
: OmniRouter val
```
#### Parameters

*   worker_name: [String](builtin-String) val
*   outgoing_boundaries: [HashMap](collections-HashMap)\[[String](builtin-String) val, [OutgoingBoundary](wallaroo-core-boundary-OutgoingBoundary) tag, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val
*   local_sinks: [HashMap](collections-HashMap)\[[U128](builtin-U128) val, [Consumer](wallaroo-core-common-Consumer) tag, [HashEq](collections-HashEq)\[[U128](builtin-U128) val\] val\] val

#### Returns

* [OmniRouter](wallaroo-core-topology-OmniRouter) val

---

