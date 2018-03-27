# StateRunner\[S: [State](wallaroo-core-state-State) ref\]

```pony
class ref StateRunner[S: State ref] is
  Runner ref,
  ReplayableRunner ref,
  SerializableStateRunner ref
```

#### Implements

* [Runner](wallaroo-core-topology-Runner) ref
* [ReplayableRunner](wallaroo-core-topology-ReplayableRunner) ref
* [SerializableStateRunner](wallaroo-core-topology-SerializableStateRunner) ref

---

## Constructors

### create

```pony
new iso create(
  state_builder: {(): S}[S] val,
  event_log: EventLog tag,
  auth: AmbientAuth val)
: StateRunner[S] iso^
```
#### Parameters

*   state_builder: {(): S}[S] val
*   event_log: [EventLog](wallaroo-ent-recovery-EventLog) tag
*   auth: [AmbientAuth](builtin-AmbientAuth) val

#### Returns

* [StateRunner](wallaroo-core-topology-StateRunner)\[S\] iso^

---

## Public Functions

### set_step_id

```pony
fun ref set_step_id(
  id: U128 val)
: None val
```
#### Parameters

*   id: [U128](builtin-U128) val

#### Returns

* [None](builtin-None) val

---

### register_state_change

```pony
fun ref register_state_change(
  scb: StateChangeBuilder[S] val)
: U64 val
```
#### Parameters

*   scb: [StateChangeBuilder](wallaroo-core-state-StateChangeBuilder)\[S\] val

#### Returns

* [U64](builtin-U64) val

---

### replay_log_entry

```pony
fun ref replay_log_entry(
  msg_uid: U128 val,
  frac_ids: (Array[U32 val] val | None val),
  statechange_id: U64 val,
  payload: (String val | Array[U8 val] val),
  producer: Producer tag)
: None val
```
#### Parameters

*   msg_uid: [U128](builtin-U128) val
*   frac_ids: ([Array](builtin-Array)\[[U32](builtin-U32) val\] val | [None](builtin-None) val)
*   statechange_id: [U64](builtin-U64) val
*   payload: ([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)
*   producer: [Producer](wallaroo-core-common-Producer) tag

#### Returns

* [None](builtin-None) val

---

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

### rotate_log

```pony
fun box rotate_log()
: None val
```

#### Returns

* [None](builtin-None) val

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

### serialize_state

```pony
fun ref serialize_state()
: (String val | Array[U8 val] val)
```

#### Returns

* ([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)

---

### replace_serialized_state

```pony
fun ref replace_serialized_state(
  payload: (String val | Array[U8 val] val))
: None val
```
#### Parameters

*   payload: ([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)

#### Returns

* [None](builtin-None) val

---

