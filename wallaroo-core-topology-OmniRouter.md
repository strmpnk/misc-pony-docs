# OmniRouter

```pony
trait val OmniRouter is
  Equatable[OmniRouter val] ref
```

#### Implements

* [Equatable](builtin-Equatable)\[[OmniRouter](wallaroo-core-topology-OmniRouter) val\] ref

---

## Public Functions

### route_with_target_ids\[D: [Any](builtin-Any) val\]

```pony
fun box route_with_target_ids[D: Any val](
  target_ids: Array[U128 val] val,
  metric_name: String val,
  pipeline_time_spent: U64 val,
  data: D,
  producer: Producer ref,
  msg_uid: U128 val,
  frac_ids: (Array[U32 val] val | None val),
  latest_ts: U64 val,
  metrics_id: U16 val,
  worker_ingress_ts: U64 val)
: (Bool val , U64 val)
```
#### Parameters

*   target_ids: [Array](builtin-Array)\[[U128](builtin-U128) val\] val
*   metric_name: [String](builtin-String) val
*   pipeline_time_spent: [U64](builtin-U64) val
*   data: D
*   producer: [Producer](wallaroo-core-common-Producer) ref
*   msg_uid: [U128](builtin-U128) val
*   frac_ids: ([Array](builtin-Array)\[[U32](builtin-U32) val\] val | [None](builtin-None) val)
*   latest_ts: [U64](builtin-U64) val
*   metrics_id: [U16](builtin-U16) val
*   worker_ingress_ts: [U64](builtin-U64) val

#### Returns

* ([Bool](builtin-Bool) val , [U64](builtin-U64) val)

---

### add_boundary

```pony
fun val add_boundary(
  w: String val,
  boundary: OutgoingBoundary tag)
: OmniRouter val
```
#### Parameters

*   w: [String](builtin-String) val
*   boundary: [OutgoingBoundary](wallaroo-core-boundary-OutgoingBoundary) tag

#### Returns

* [OmniRouter](wallaroo-core-topology-OmniRouter) val

---

### update_route_to_proxy

```pony
fun val update_route_to_proxy(
  id: U128 val,
  pa: ProxyAddress val)
: OmniRouter val
```
#### Parameters

*   id: [U128](builtin-U128) val
*   pa: [ProxyAddress](wallaroo-core-topology-ProxyAddress) val

#### Returns

* [OmniRouter](wallaroo-core-topology-OmniRouter) val

---

### update_route_to_step

```pony
fun val update_route_to_step(
  id: U128 val,
  step: Consumer tag)
: OmniRouter val
```
#### Parameters

*   id: [U128](builtin-U128) val
*   step: [Consumer](wallaroo-core-common-Consumer) tag

#### Returns

* [OmniRouter](wallaroo-core-topology-OmniRouter) val

---

### update_stateless_partition_router

```pony
fun val update_stateless_partition_router(
  id: U128 val,
  pr: StatelessPartitionRouter val)
: OmniRouter val
```
#### Parameters

*   id: [U128](builtin-U128) val
*   pr: [StatelessPartitionRouter](wallaroo-core-topology-StatelessPartitionRouter) val

#### Returns

* [OmniRouter](wallaroo-core-topology-OmniRouter) val

---

### routes

```pony
fun box routes()
: Array[Consumer tag] val
```

#### Returns

* [Array](builtin-Array)\[[Consumer](wallaroo-core-common-Consumer) tag\] val

---

### get_outgoing_boundaries_sorted

```pony
fun box get_outgoing_boundaries_sorted()
: Array[(String val , OutgoingBoundary tag)] val
```

#### Returns

* [Array](builtin-Array)\[([String](builtin-String) val , [OutgoingBoundary](wallaroo-core-boundary-OutgoingBoundary) tag)\] val

---

### routes_not_in

```pony
fun box routes_not_in(
  router: OmniRouter val)
: Array[Consumer tag] val
```
#### Parameters

*   router: [OmniRouter](wallaroo-core-topology-OmniRouter) val

#### Returns

* [Array](builtin-Array)\[[Consumer](wallaroo-core-common-Consumer) tag\] val

---

### boundaries

```pony
fun box boundaries()
: HashMap[String val, OutgoingBoundary tag, HashEq[String val] val] val
```

#### Returns

* [HashMap](collections-HashMap)\[[String](builtin-String) val, [OutgoingBoundary](wallaroo-core-boundary-OutgoingBoundary) tag, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val

---

### blueprint

```pony
fun box blueprint()
: OmniRouterBlueprint val
```

#### Returns

* [OmniRouterBlueprint](wallaroo-core-topology-OmniRouterBlueprint) val

---

### eq

```pony
fun box eq(
  that: OmniRouter val)
: Bool val
```
#### Parameters

*   that: [OmniRouter](wallaroo-core-topology-OmniRouter) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: OmniRouter val)
: Bool val
```
#### Parameters

*   that: [OmniRouter](wallaroo-core-topology-OmniRouter) val

#### Returns

* [Bool](builtin-Bool) val

---

