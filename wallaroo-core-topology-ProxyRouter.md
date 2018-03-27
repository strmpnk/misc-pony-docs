# ProxyRouter

```pony
class val ProxyRouter is
  Router val,
  Equatable[ProxyRouter val] ref
```

#### Implements

* [Router](wallaroo-core-topology-Router) val
* [Equatable](builtin-Equatable)\[[ProxyRouter](wallaroo-core-topology-ProxyRouter) val\] ref

---

## Constructors

### create

```pony
new val create(
  worker_name: String val,
  target: OutgoingBoundary tag,
  target_proxy_address: ProxyAddress val,
  auth: AmbientAuth val)
: ProxyRouter val^
```
#### Parameters

*   worker_name: [String](builtin-String) val
*   target: [OutgoingBoundary](wallaroo-core-boundary-OutgoingBoundary) tag
*   target_proxy_address: [ProxyAddress](wallaroo-core-topology-ProxyAddress) val
*   auth: [AmbientAuth](builtin-AmbientAuth) val

#### Returns

* [ProxyRouter](wallaroo-core-topology-ProxyRouter) val^

---

## Public Functions

### route\[D: [Any](builtin-Any) val\]

```pony
fun box route[D: Any val](
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

### copy_with_new_target_id

```pony
fun box copy_with_new_target_id(
  target_id: U128 val)
: ProxyRouter val
```
#### Parameters

*   target_id: [U128](builtin-U128) val

#### Returns

* [ProxyRouter](wallaroo-core-topology-ProxyRouter) val

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

### update_proxy_address

```pony
fun box update_proxy_address(
  pa: ProxyAddress val)
: ProxyRouter val
```
#### Parameters

*   pa: [ProxyAddress](wallaroo-core-topology-ProxyAddress) val

#### Returns

* [ProxyRouter](wallaroo-core-topology-ProxyRouter) val

---

### update_boundary

```pony
fun val update_boundary(
  ob: HashMap[String val, OutgoingBoundary tag, HashEq[String val] val] box)
: ProxyRouter val
```
#### Parameters

*   ob: [HashMap](collections-HashMap)\[[String](builtin-String) val, [OutgoingBoundary](wallaroo-core-boundary-OutgoingBoundary) tag, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] box

#### Returns

* [ProxyRouter](wallaroo-core-topology-ProxyRouter) val

---

### proxy_address

```pony
fun box proxy_address()
: ProxyAddress val
```

#### Returns

* [ProxyAddress](wallaroo-core-topology-ProxyAddress) val

---

### eq

```pony
fun box eq(
  that: ProxyRouter val)
: Bool val
```
#### Parameters

*   that: [ProxyRouter](wallaroo-core-topology-ProxyRouter) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: ProxyRouter val)
: Bool val
```
#### Parameters

*   that: [ProxyRouter](wallaroo-core-topology-ProxyRouter) val

#### Returns

* [Bool](builtin-Bool) val

---

