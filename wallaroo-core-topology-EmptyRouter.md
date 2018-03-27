# EmptyRouter

```pony
class val EmptyRouter is
  Router val
```

#### Implements

* [Router](wallaroo-core-topology-Router) val

---

## Constructors

### create

```pony
new iso create()
: EmptyRouter iso^
```

#### Returns

* [EmptyRouter](wallaroo-core-topology-EmptyRouter) iso^

---

## Public Functions

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

