# ComputationRunner\[In: [Any](builtin-Any) val, Out: [Any](builtin-Any) val\]

```pony
class ref ComputationRunner[In: Any val, Out: Any val]
```

## Constructors

### create

```pony
new iso create(
  computation: Computation[In, Out] val,
  next: Runner iso)
: ComputationRunner[In, Out] iso^
```
#### Parameters

*   computation: [Computation](wallaroo-core-topology-Computation)\[In, Out\] val
*   next: [Runner](wallaroo-core-topology-Runner) iso

#### Returns

* [ComputationRunner](wallaroo-core-topology-ComputationRunner)\[In, Out\] iso^

---

## Public Functions

### run\[D: [Any](builtin-Any) val\]

```pony
fun ref run[D: Any val](
  metric_name: String val,
  pipeline_time_spent: U64 val,
  data: D,
  producer: Producer ref,
  router: Router val,
  omni_router: OmniRouter val,
  i_msg_uid: U128 val,
  frac_ids: (Array[U32 val] val | None val),
  latest_ts: U64 val,
  metrics_id: U16 val,
  worker_ingress_ts: U64 val,
  metrics_reporter: MetricsReporter ref)
: (Bool val , U64 val)
```
#### Parameters

*   metric_name: [String](builtin-String) val
*   pipeline_time_spent: [U64](builtin-U64) val
*   data: D
*   producer: [Producer](wallaroo-core-common-Producer) ref
*   router: [Router](wallaroo-core-topology-Router) val
*   omni_router: [OmniRouter](wallaroo-core-topology-OmniRouter) val
*   i_msg_uid: [U128](builtin-U128) val
*   frac_ids: ([Array](builtin-Array)\[[U32](builtin-U32) val\] val | [None](builtin-None) val)
*   latest_ts: [U64](builtin-U64) val
*   metrics_id: [U16](builtin-U16) val
*   worker_ingress_ts: [U64](builtin-U64) val
*   metrics_reporter: [MetricsReporter](wallaroo-core-metrics-MetricsReporter) ref

#### Returns

* ([Bool](builtin-Bool) val , [U64](builtin-U64) val)

---

### name

```pony
fun box name()
: String val
```

#### Returns

* [String](builtin-String) val

---

### state_name

```pony
fun box state_name()
: String val
```

#### Returns

* [String](builtin-String) val

---

### clone_router_and_set_input_type

```pony
fun box clone_router_and_set_input_type(
  r: Router val)
: Router val
```
#### Parameters

*   r: [Router](wallaroo-core-topology-Router) val

#### Returns

* [Router](wallaroo-core-topology-Router) val

---

