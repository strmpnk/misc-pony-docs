# LocalStatelessPartitionRouter

```pony
class val LocalStatelessPartitionRouter is
  StatelessPartitionRouter val
```

#### Implements

* [StatelessPartitionRouter](wallaroo-core-topology-StatelessPartitionRouter) val

---

## Constructors

### create

```pony
new val create(
  p_id: U128 val,
  worker_name: String val,
  s_ids: HashMap[U64 val, U128 val, HashEq[U64 val] val] val,
  partition_routes: HashMap[U64 val, (Step tag | ProxyRouter val), HashEq[U64 val] val] val,
  steps_per_worker: USize val)
: LocalStatelessPartitionRouter val^
```
#### Parameters

*   p_id: [U128](builtin-U128) val
*   worker_name: [String](builtin-String) val
*   s_ids: [HashMap](collections-HashMap)\[[U64](builtin-U64) val, [U128](builtin-U128) val, [HashEq](collections-HashEq)\[[U64](builtin-U64) val\] val\] val
*   partition_routes: [HashMap](collections-HashMap)\[[U64](builtin-U64) val, ([Step](wallaroo-core-topology-Step) tag | [ProxyRouter](wallaroo-core-topology-ProxyRouter) val), [HashEq](collections-HashEq)\[[U64](builtin-U64) val\] val\] val
*   steps_per_worker: [USize](builtin-USize) val

#### Returns

* [LocalStatelessPartitionRouter](wallaroo-core-topology-LocalStatelessPartitionRouter) val^

---

## Public Functions

### size

```pony
fun box size()
: USize val
```

#### Returns

* [USize](builtin-USize) val

---

### partition_id

```pony
fun box partition_id()
: U128 val
```

#### Returns

* [U128](builtin-U128) val

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

### update_route

```pony
fun box update_route(
  partition_id': U64 val,
  target: (Step tag | ProxyRouter val))
: StatelessPartitionRouter val ?
```
#### Parameters

*   partition_id': [U64](builtin-U64) val
*   target: ([Step](wallaroo-core-topology-Step) tag | [ProxyRouter](wallaroo-core-topology-ProxyRouter) val)

#### Returns

* [StatelessPartitionRouter](wallaroo-core-topology-StatelessPartitionRouter) val ?

---

### update_boundaries

```pony
fun box update_boundaries(
  ob: HashMap[String val, OutgoingBoundary tag, HashEq[String val] val] box)
: StatelessPartitionRouter val
```
#### Parameters

*   ob: [HashMap](collections-HashMap)\[[String](builtin-String) val, [OutgoingBoundary](wallaroo-core-boundary-OutgoingBoundary) tag, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] box

#### Returns

* [StatelessPartitionRouter](wallaroo-core-topology-StatelessPartitionRouter) val

---

### calculate_shrink

```pony
fun box calculate_shrink(
  remaining_workers: Array[String val] val)
: StatelessPartitionRouter val
```
#### Parameters

*   remaining_workers: [Array](builtin-Array)\[[String](builtin-String) val\] val

#### Returns

* [StatelessPartitionRouter](wallaroo-core-topology-StatelessPartitionRouter) val

---

### blueprint

```pony
fun box blueprint()
: StatelessPartitionRouterBlueprint val
```

#### Returns

* [StatelessPartitionRouterBlueprint](wallaroo-core-topology-StatelessPartitionRouterBlueprint) val

---

### distribution_digest

```pony
fun box distribution_digest()
: HashMap[String val, Array[String val] val, HashEq[String val] val] val
```

#### Returns

* [HashMap](collections-HashMap)\[[String](builtin-String) val, [Array](builtin-Array)\[[String](builtin-String) val\] val, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val

---

### eq

```pony
fun box eq(
  that: StatelessPartitionRouter val)
: Bool val
```
#### Parameters

*   that: [StatelessPartitionRouter](wallaroo-core-topology-StatelessPartitionRouter) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: StatelessPartitionRouter val)
: Bool val
```
#### Parameters

*   that: [StatelessPartitionRouter](wallaroo-core-topology-StatelessPartitionRouter) val

#### Returns

* [Bool](builtin-Bool) val

---

## Private Functions

### _partition_routes_eq

```pony
fun box _partition_routes_eq(
  opr: HashMap[U64 val, (Step tag | ProxyRouter val), HashEq[U64 val] val] val)
: Bool val
```
#### Parameters

*   opr: [HashMap](collections-HashMap)\[[U64](builtin-U64) val, ([Step](wallaroo-core-topology-Step) tag | [ProxyRouter](wallaroo-core-topology-ProxyRouter) val), [HashEq](collections-HashEq)\[[U64](builtin-U64) val\] val\] val

#### Returns

* [Bool](builtin-Bool) val

---

