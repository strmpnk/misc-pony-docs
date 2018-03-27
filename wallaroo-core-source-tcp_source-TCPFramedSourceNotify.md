# TCPFramedSourceNotify\[In: [Any](builtin-Any) val\]

```pony
class ref TCPFramedSourceNotify[In: Any val] is
  TCPSourceNotify ref
```

#### Implements

* [TCPSourceNotify](wallaroo-core-source-tcp_source-TCPSourceNotify) ref

---

## Constructors

### create

```pony
new iso create(
  pipeline_name: String val,
  env: Env val,
  auth: AmbientAuth val,
  handler: FramedSourceHandler[In] val,
  runner_builder: RunnerBuilder val,
  router: Router val,
  metrics_reporter: MetricsReporter iso,
  event_log: EventLog tag,
  target_router: Router val,
  pre_state_target_ids: Array[U128 val] val = seq)
: TCPFramedSourceNotify[In] iso^
```
#### Parameters

*   pipeline_name: [String](builtin-String) val
*   env: [Env](builtin-Env) val
*   auth: [AmbientAuth](builtin-AmbientAuth) val
*   handler: [FramedSourceHandler](wallaroo-core-source-FramedSourceHandler)\[In\] val
*   runner_builder: [RunnerBuilder](wallaroo-core-topology-RunnerBuilder) val
*   router: [Router](wallaroo-core-topology-Router) val
*   metrics_reporter: [MetricsReporter](wallaroo-core-metrics-MetricsReporter) iso
*   event_log: [EventLog](wallaroo-ent-recovery-EventLog) tag
*   target_router: [Router](wallaroo-core-topology-Router) val
*   pre_state_target_ids: [Array](builtin-Array)\[[U128](builtin-U128) val\] val = seq

#### Returns

* [TCPFramedSourceNotify](wallaroo-core-source-tcp_source-TCPFramedSourceNotify)\[In\] iso^

---

## Public Functions

### routes

```pony
fun box routes()
: Array[Consumer tag] val
```

#### Returns

* [Array](builtin-Array)\[[Consumer](wallaroo-core-common-Consumer) tag\] val

---

### received

```pony
fun ref received(
  conn: TCPSource ref,
  data: Array[U8 val] iso)
: Bool val
```
#### Parameters

*   conn: [TCPSource](wallaroo-core-source-tcp_source-TCPSource) ref
*   data: [Array](builtin-Array)\[[U8](builtin-U8) val\] iso

#### Returns

* [Bool](builtin-Bool) val

---

### update_router

```pony
fun ref update_router(
  router: Router val)
: None val
```
#### Parameters

*   router: [Router](wallaroo-core-topology-Router) val

#### Returns

* [None](builtin-None) val

---

### update_boundaries

```pony
fun ref update_boundaries(
  obs: HashMap[String val, OutgoingBoundary tag, HashEq[String val] val] box)
: None val
```
#### Parameters

*   obs: [HashMap](collections-HashMap)\[[String](builtin-String) val, [OutgoingBoundary](wallaroo-core-boundary-OutgoingBoundary) tag, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] box

#### Returns

* [None](builtin-None) val

---

### accepted

```pony
fun ref accepted(
  conn: TCPSource ref)
: None val
```
#### Parameters

*   conn: [TCPSource](wallaroo-core-source-tcp_source-TCPSource) ref

#### Returns

* [None](builtin-None) val

---

### closed

```pony
fun ref closed(
  conn: TCPSource ref)
: None val
```
#### Parameters

*   conn: [TCPSource](wallaroo-core-source-tcp_source-TCPSource) ref

#### Returns

* [None](builtin-None) val

---

### connecting

```pony
fun ref connecting(
  conn: TCPSource ref,
  count: U32 val)
: None val
```
#### Parameters

*   conn: [TCPSource](wallaroo-core-source-tcp_source-TCPSource) ref
*   count: [U32](builtin-U32) val

#### Returns

* [None](builtin-None) val

---

### connected

```pony
fun ref connected(
  conn: TCPSource ref)
: None val
```
#### Parameters

*   conn: [TCPSource](wallaroo-core-source-tcp_source-TCPSource) ref

#### Returns

* [None](builtin-None) val

---

### connect_failed

```pony
fun ref connect_failed(
  conn: TCPSource ref)
: None val
```
#### Parameters

*   conn: [TCPSource](wallaroo-core-source-tcp_source-TCPSource) ref

#### Returns

* [None](builtin-None) val

---

### expect

```pony
fun ref expect(
  conn: TCPSource ref,
  qty: USize val)
: USize val
```
#### Parameters

*   conn: [TCPSource](wallaroo-core-source-tcp_source-TCPSource) ref
*   qty: [USize](builtin-USize) val

#### Returns

* [USize](builtin-USize) val

---

