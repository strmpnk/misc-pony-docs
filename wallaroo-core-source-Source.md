# Source

```pony
interface tag Source is
  DisposableActor tag,
  BoundaryUpdateable tag
```

#### Implements

* [DisposableActor](builtin-DisposableActor) tag
* [BoundaryUpdateable](wallaroo-core-common-BoundaryUpdateable) tag

---

## Public Behaviours

### update_router

```pony
be update_router(
  router: PartitionRouter val)
```
#### Parameters

*   router: [PartitionRouter](wallaroo-core-topology-PartitionRouter) val

---

### add_boundary_builders

```pony
be add_boundary_builders(
  boundary_builders: HashMap[String val, OutgoingBoundaryBuilder val, HashEq[String val] val] val)
```
#### Parameters

*   boundary_builders: [HashMap](collections-HashMap)\[[String](builtin-String) val, [OutgoingBoundaryBuilder](wallaroo-core-boundary-OutgoingBoundaryBuilder) val, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val

---

### reconnect_boundary

```pony
be reconnect_boundary(
  target_worker_name: String val)
```
#### Parameters

*   target_worker_name: [String](builtin-String) val

---

### mute

```pony
be mute(
  c: Consumer tag)
```
#### Parameters

*   c: [Consumer](wallaroo-core-common-Consumer) tag

---

### unmute

```pony
be unmute(
  c: Consumer tag)
```
#### Parameters

*   c: [Consumer](wallaroo-core-common-Consumer) tag

---

### dispose

```pony
be dispose()
```

---

### remove_boundary

```pony
be remove_boundary(
  worker: String val)
```
#### Parameters

*   worker: [String](builtin-String) val

---

