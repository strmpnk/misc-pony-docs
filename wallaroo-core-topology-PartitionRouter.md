# PartitionRouter

```pony
trait val PartitionRouter is
  Router val,
  Equatable[PartitionRouter val] ref
```

#### Implements

* [Router](wallaroo-core-topology-Router) val
* [Equatable](builtin-Equatable)\[[PartitionRouter](wallaroo-core-topology-PartitionRouter) val\] ref

---

## Public Functions

### state_name

```pony
fun box state_name()
: String val
```

#### Returns

* [String](builtin-String) val

---

### local_map

```pony
fun box local_map()
: HashMap[U128 val, Step tag, HashEq[U128 val] val] val
```

#### Returns

* [HashMap](collections-HashMap)\[[U128](builtin-U128) val, [Step](wallaroo-core-topology-Step) tag, [HashEq](collections-HashEq)\[[U128](builtin-U128) val\] val\] val

---

### register_routes

```pony
fun box register_routes(
  router: Router val,
  route_builder': RouteBuilder val)
: None val
```
#### Parameters

*   router: [Router](wallaroo-core-topology-Router) val
*   route_builder': [RouteBuilder](wallaroo-core-routing-RouteBuilder) val

#### Returns

* [None](builtin-None) val

---

### update_route\[K: ([Hashable](collections-Hashable) val & [Equatable](builtin-Equatable)\[K\] val)\]

```pony
fun box update_route[K: (Hashable val & Equatable[K] val)](
  raw_k: K,
  target: (Step tag | ProxyRouter val))
: PartitionRouter val ?
```
#### Parameters

*   raw_k: K
*   target: ([Step](wallaroo-core-topology-Step) tag | [ProxyRouter](wallaroo-core-topology-ProxyRouter) val)

#### Returns

* [PartitionRouter](wallaroo-core-topology-PartitionRouter) val ?

---

### rebalance_steps_grow

```pony
fun box rebalance_steps_grow(
  target_workers: Array[(String val , OutgoingBoundary tag)] val,
  worker_count: USize val,
  state_name': String val,
  router_registry: RouterRegistry ref)
: None val
```
#### Parameters

*   target_workers: [Array](builtin-Array)\[([String](builtin-String) val , [OutgoingBoundary](wallaroo-core-boundary-OutgoingBoundary) tag)\] val
*   worker_count: [USize](builtin-USize) val
*   state_name': [String](builtin-String) val
*   router_registry: [RouterRegistry](wallaroo-ent-router_registry-RouterRegistry) ref

#### Returns

* [None](builtin-None) val

---

### rebalance_steps_shrink

```pony
fun box rebalance_steps_shrink(
  target_workers: Array[(String val , OutgoingBoundary tag)] val,
  state_name': String val,
  router_registry: RouterRegistry ref)
: None val
```
#### Parameters

*   target_workers: [Array](builtin-Array)\[([String](builtin-String) val , [OutgoingBoundary](wallaroo-core-boundary-OutgoingBoundary) tag)\] val
*   state_name': [String](builtin-String) val
*   router_registry: [RouterRegistry](wallaroo-ent-router_registry-RouterRegistry) ref

#### Returns

* [None](builtin-None) val

---

### size

```pony
fun box size()
: USize val
```

#### Returns

* [USize](builtin-USize) val

---

### update_boundaries

```pony
fun box update_boundaries(
  ob: HashMap[String val, OutgoingBoundary tag, HashEq[String val] val] box)
: PartitionRouter val
```
#### Parameters

*   ob: [HashMap](collections-HashMap)\[[String](builtin-String) val, [OutgoingBoundary](wallaroo-core-boundary-OutgoingBoundary) tag, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] box

#### Returns

* [PartitionRouter](wallaroo-core-topology-PartitionRouter) val

---

### blueprint

```pony
fun box blueprint()
: PartitionRouterBlueprint val
```

#### Returns

* [PartitionRouterBlueprint](wallaroo-core-topology-PartitionRouterBlueprint) val

---

### distribution_digest

```pony
fun box distribution_digest()
: HashMap[String val, Array[String val] val, HashEq[String val] val] val
```

#### Returns

* [HashMap](collections-HashMap)\[[String](builtin-String) val, [Array](builtin-Array)\[[String](builtin-String) val\] val, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val

---

### route_builder

```pony
fun box route_builder()
: RouteBuilder val
```

#### Returns

* [RouteBuilder](wallaroo-core-routing-RouteBuilder) val

---

### route\[D: [Any](builtin-Any) val\]

```pony
fun box route[D: Any val](
  metric_name: String val,
  pipeline_time_spent: U64 val,
  data: D,
  producer: Producer ref,
  i_msg_uid: U128 val,
  frac_ids: (Array[U32 val] val | None val),
  latest_ts: U64 val,
  metrics_id: U16 val,
  worker_ingress_ts: U64 val)
: (Bool val , U64 val)
```
#### Parameters

*   metric_name: [String](builtin-String) val
*   pipeline_time_spent: [U64](builtin-U64) val
*   data: D
*   producer: [Producer](wallaroo-core-common-Producer) ref
*   i_msg_uid: [U128](builtin-U128) val
*   frac_ids: ([Array](builtin-Array)\[[U32](builtin-U32) val\] val | [None](builtin-None) val)
*   latest_ts: [U64](builtin-U64) val
*   metrics_id: [U16](builtin-U16) val
*   worker_ingress_ts: [U64](builtin-U64) val

#### Returns

* ([Bool](builtin-Bool) val , [U64](builtin-U64) val)

---

### routes

```pony
fun box routes()
: Array[Consumer tag] val
```

#### Returns

* [Array](builtin-Array)\[[Consumer](wallaroo-core-common-Consumer) tag\] val

---

### routes_not_in

```pony
fun box routes_not_in(
  router: Router val)
: Array[Consumer tag] val
```
#### Parameters

*   router: [Router](wallaroo-core-topology-Router) val

#### Returns

* [Array](builtin-Array)\[[Consumer](wallaroo-core-common-Consumer) tag\] val

---

### eq

```pony
fun box eq(
  that: PartitionRouter val)
: Bool val
```
#### Parameters

*   that: [PartitionRouter](wallaroo-core-topology-PartitionRouter) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: PartitionRouter val)
: Bool val
```
#### Parameters

*   that: [PartitionRouter](wallaroo-core-topology-PartitionRouter) val

#### Returns

* [Bool](builtin-Bool) val

---

