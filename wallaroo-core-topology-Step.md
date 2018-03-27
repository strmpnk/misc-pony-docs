# Step

```pony
actor tag Step is
  Producer tag,
  Consumer tag
```

#### Implements

* [Producer](wallaroo-core-common-Producer) tag
* [Consumer](wallaroo-core-common-Consumer) tag

---

## Constructors

### create

```pony
new tag create(
  runner: Runner iso,
  metrics_reporter: MetricsReporter iso,
  id: U128 val,
  route_builder: RouteBuilder val,
  event_log: EventLog tag,
  recovery_replayer: RecoveryReplayer tag,
  outgoing_boundaries: HashMap[String val, OutgoingBoundary tag, HashEq[String val] val] val,
  router: Router val = seq,
  omni_router: OmniRouter val = seq)
: Step tag^
```
#### Parameters

*   runner: [Runner](wallaroo-core-topology-Runner) iso
*   metrics_reporter: [MetricsReporter](wallaroo-core-metrics-MetricsReporter) iso
*   id: [U128](builtin-U128) val
*   route_builder: [RouteBuilder](wallaroo-core-routing-RouteBuilder) val
*   event_log: [EventLog](wallaroo-ent-recovery-EventLog) tag
*   recovery_replayer: [RecoveryReplayer](wallaroo-ent-recovery-RecoveryReplayer) tag
*   outgoing_boundaries: [HashMap](collections-HashMap)\[[String](builtin-String) val, [OutgoingBoundary](wallaroo-core-boundary-OutgoingBoundary) tag, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val
*   router: [Router](wallaroo-core-topology-Router) val = seq
*   omni_router: [OmniRouter](wallaroo-core-topology-OmniRouter) val = seq

#### Returns

* [Step](wallaroo-core-topology-Step) tag^

---

## Public Behaviours

### application_begin_reporting

```pony
be application_begin_reporting(
  initializer: LocalTopologyInitializer tag)
```
#### Parameters

*   initializer: [LocalTopologyInitializer](wallaroo-core-initialization-LocalTopologyInitializer) tag

---

### application_created

```pony
be application_created(
  initializer: LocalTopologyInitializer tag,
  omni_router: OmniRouter val)
```
#### Parameters

*   initializer: [LocalTopologyInitializer](wallaroo-core-initialization-LocalTopologyInitializer) tag
*   omni_router: [OmniRouter](wallaroo-core-topology-OmniRouter) val

---

### application_initialized

```pony
be application_initialized(
  initializer: LocalTopologyInitializer tag)
```
#### Parameters

*   initializer: [LocalTopologyInitializer](wallaroo-core-initialization-LocalTopologyInitializer) tag

---

### application_ready_to_work

```pony
be application_ready_to_work(
  initializer: LocalTopologyInitializer tag)
```
#### Parameters

*   initializer: [LocalTopologyInitializer](wallaroo-core-initialization-LocalTopologyInitializer) tag

---

### update_route_builder

```pony
be update_route_builder(
  route_builder: RouteBuilder val)
```
#### Parameters

*   route_builder: [RouteBuilder](wallaroo-core-routing-RouteBuilder) val

---

### register_routes

```pony
be register_routes(
  router: Router val,
  route_builder: RouteBuilder val)
```
#### Parameters

*   router: [Router](wallaroo-core-topology-Router) val
*   route_builder: [RouteBuilder](wallaroo-core-routing-RouteBuilder) val

---

### update_router

```pony
be update_router(
  router: Router val)
```
#### Parameters

*   router: [Router](wallaroo-core-topology-Router) val

---

### update_omni_router

```pony
be update_omni_router(
  omni_router: OmniRouter val)
```
#### Parameters

*   omni_router: [OmniRouter](wallaroo-core-topology-OmniRouter) val

---

### add_boundaries

```pony
be add_boundaries(
  boundaries: HashMap[String val, OutgoingBoundary tag, HashEq[String val] val] val)
```
#### Parameters

*   boundaries: [HashMap](collections-HashMap)\[[String](builtin-String) val, [OutgoingBoundary](wallaroo-core-boundary-OutgoingBoundary) tag, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val

---

### remove_boundary

```pony
be remove_boundary(
  worker: String val)
```
#### Parameters

*   worker: [String](builtin-String) val

---

### remove_route_for

```pony
be remove_route_for(
  step: Consumer tag)
```
#### Parameters

*   step: [Consumer](wallaroo-core-common-Consumer) tag

---

### run\[D: [Any](builtin-Any) val\]

```pony
be run[D: Any val](
  metric_name: String val,
  pipeline_time_spent: U64 val,
  data: D,
  i_producer: Producer tag,
  msg_uid: U128 val,
  frac_ids: (Array[U32 val] val | None val),
  i_seq_id: U64 val,
  i_route_id: U64 val,
  latest_ts: U64 val,
  metrics_id: U16 val,
  worker_ingress_ts: U64 val)
```
#### Parameters

*   metric_name: [String](builtin-String) val
*   pipeline_time_spent: [U64](builtin-U64) val
*   data: D
*   i_producer: [Producer](wallaroo-core-common-Producer) tag
*   msg_uid: [U128](builtin-U128) val
*   frac_ids: ([Array](builtin-Array)\[[U32](builtin-U32) val\] val | [None](builtin-None) val)
*   i_seq_id: [U64](builtin-U64) val
*   i_route_id: [U64](builtin-U64) val
*   latest_ts: [U64](builtin-U64) val
*   metrics_id: [U16](builtin-U16) val
*   worker_ingress_ts: [U64](builtin-U64) val

---

### replay_run\[D: [Any](builtin-Any) val\]

```pony
be replay_run[D: Any val](
  metric_name: String val,
  pipeline_time_spent: U64 val,
  data: D,
  i_producer: Producer tag,
  msg_uid: U128 val,
  frac_ids: (Array[U32 val] val | None val),
  i_seq_id: U64 val,
  i_route_id: U64 val,
  latest_ts: U64 val,
  metrics_id: U16 val,
  worker_ingress_ts: U64 val)
```
#### Parameters

*   metric_name: [String](builtin-String) val
*   pipeline_time_spent: [U64](builtin-U64) val
*   data: D
*   i_producer: [Producer](wallaroo-core-common-Producer) tag
*   msg_uid: [U128](builtin-U128) val
*   frac_ids: ([Array](builtin-Array)\[[U32](builtin-U32) val\] val | [None](builtin-None) val)
*   i_seq_id: [U64](builtin-U64) val
*   i_route_id: [U64](builtin-U64) val
*   latest_ts: [U64](builtin-U64) val
*   metrics_id: [U16](builtin-U16) val
*   worker_ingress_ts: [U64](builtin-U64) val

---

### request_ack

```pony
be request_ack()
```

---

### replay_log_entry

```pony
be replay_log_entry(
  uid: U128 val,
  frac_ids: (Array[U32 val] val | None val),
  statechange_id: U64 val,
  payload: (String val | Array[U8 val] val))
```
#### Parameters

*   uid: [U128](builtin-U128) val
*   frac_ids: ([Array](builtin-Array)\[[U32](builtin-U32) val\] val | [None](builtin-None) val)
*   statechange_id: [U64](builtin-U64) val
*   payload: ([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)

---

### initialize_seq_id_on_recovery

```pony
be initialize_seq_id_on_recovery(
  seq_id: U64 val)
```
#### Parameters

*   seq_id: [U64](builtin-U64) val

---

### clear_deduplication_list

```pony
be clear_deduplication_list()
```

---

### dispose

```pony
be dispose()
```

---

### register_producer

```pony
be register_producer(
  producer: Producer tag)
```
#### Parameters

*   producer: [Producer](wallaroo-core-common-Producer) tag

---

### unregister_producer

```pony
be unregister_producer(
  producer: Producer tag)
```
#### Parameters

*   producer: [Producer](wallaroo-core-common-Producer) tag

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

### receive_state

```pony
be receive_state(
  state: (String val | Array[U8 val] val))
```
#### Parameters

*   state: ([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)

---

### send_state_to_neighbour

```pony
be send_state_to_neighbour(
  neighbour: Step tag)
```
#### Parameters

*   neighbour: [Step](wallaroo-core-topology-Step) tag

---

### send_state\[K: ([Hashable](collections-Hashable) val & [Equatable](builtin-Equatable)\[K\] val)\]

```pony
be send_state[K: (Hashable val & Equatable[K] val)](
  boundary: OutgoingBoundary tag,
  state_name: String val,
  key: K)
```
#### Parameters

*   boundary: [OutgoingBoundary](wallaroo-core-boundary-OutgoingBoundary) tag
*   state_name: [String](builtin-String) val
*   key: K

---

### snapshot_state

```pony
be snapshot_state()
```

---

### log_flushed

```pony
be log_flushed(
  low_watermark: U64 val)
```
#### Parameters

*   low_watermark: [U64](builtin-U64) val

---

### update_watermark

```pony
be update_watermark(
  route_id: U64 val,
  seq_id: U64 val)
```
#### Parameters

*   route_id: [U64](builtin-U64) val
*   seq_id: [U64](builtin-U64) val

---

## Public Functions

### report_route_ready_to_work

```pony
fun ref report_route_ready_to_work(
  r: RouteLogic ref)
: None val
```
#### Parameters

*   r: [RouteLogic](wallaroo-core-routing-RouteLogic) ref

#### Returns

* [None](builtin-None) val

---

### next_sequence_id

```pony
fun ref next_sequence_id()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### current_sequence_id

```pony
fun ref current_sequence_id()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### flush

```pony
fun ref flush(
  low_watermark: U64 val)
: None val
```
#### Parameters

*   low_watermark: [U64](builtin-U64) val

#### Returns

* [None](builtin-None) val

---

### route_to

```pony
fun ref route_to(
  c: Consumer tag)
: (Route ref | None val)
```
#### Parameters

*   c: [Consumer](wallaroo-core-common-Consumer) tag

#### Returns

* ([Route](wallaroo-core-routing-Route) ref | [None](builtin-None) val)

---

### bookkeeping

```pony
fun ref bookkeeping(
  o_route_id: U64 val,
  o_seq_id: U64 val)
: None val
```
#### Parameters

*   o_route_id: [U64](builtin-U64) val
*   o_seq_id: [U64](builtin-U64) val

#### Returns

* [None](builtin-None) val

---

## Private Functions

### _report_ready_to_work

```pony
fun ref _report_ready_to_work()
: None val
```

#### Returns

* [None](builtin-None) val

---

### _update_router

```pony
fun ref _update_router(
  router: Router val)
: None val
```
#### Parameters

*   router: [Router](wallaroo-core-topology-Router) val

#### Returns

* [None](builtin-None) val

---

### _add_boundaries

```pony
fun ref _add_boundaries(
  boundaries: HashMap[String val, OutgoingBoundary tag, HashEq[String val] val] val)
: None val
```
#### Parameters

*   boundaries: [HashMap](collections-HashMap)\[[String](builtin-String) val, [OutgoingBoundary](wallaroo-core-boundary-OutgoingBoundary) tag, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val

#### Returns

* [None](builtin-None) val

---

### _run\[D: [Any](builtin-Any) val\]

```pony
fun ref _run[D: Any val](
  metric_name: String val,
  pipeline_time_spent: U64 val,
  data: D,
  i_producer: Producer tag,
  msg_uid: U128 val,
  frac_ids: (Array[U32 val] val | None val),
  i_seq_id: U64 val,
  i_route_id: U64 val,
  latest_ts: U64 val,
  metrics_id: U16 val,
  worker_ingress_ts: U64 val)
: None val
```
#### Parameters

*   metric_name: [String](builtin-String) val
*   pipeline_time_spent: [U64](builtin-U64) val
*   data: D
*   i_producer: [Producer](wallaroo-core-common-Producer) tag
*   msg_uid: [U128](builtin-U128) val
*   frac_ids: ([Array](builtin-Array)\[[U32](builtin-U32) val\] val | [None](builtin-None) val)
*   i_seq_id: [U64](builtin-U64) val
*   i_route_id: [U64](builtin-U64) val
*   latest_ts: [U64](builtin-U64) val
*   metrics_id: [U16](builtin-U16) val
*   worker_ingress_ts: [U64](builtin-U64) val

#### Returns

* [None](builtin-None) val

---

### _is_duplicate

```pony
fun ref _is_duplicate(
  msg_uid: U128 val,
  frac_ids: (Array[U32 val] val | None val))
: Bool val
```
#### Parameters

*   msg_uid: [U128](builtin-U128) val
*   frac_ids: ([Array](builtin-Array)\[[U32](builtin-U32) val\] val | [None](builtin-None) val)

#### Returns

* [Bool](builtin-Bool) val

---

### _acker

```pony
fun ref _acker()
: Acker ref
```

#### Returns

* [Acker](wallaroo-ent-watermarking-Acker) ref

---

### _update_watermark

```pony
fun ref _update_watermark(
  route_id: U64 val,
  seq_id: U64 val)
: None val
```
#### Parameters

*   route_id: [U64](builtin-U64) val
*   seq_id: [U64](builtin-U64) val

#### Returns

* [None](builtin-None) val

---

