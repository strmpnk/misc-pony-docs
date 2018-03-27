# TCPSource

# TCPSource

## Future work
* Switch to requesting credits via promise


```pony
actor tag TCPSource is
  Producer tag
```

#### Implements

* [Producer](wallaroo-core-common-Producer) tag

---

## Constructors

### _accept

```pony
new tag _accept(
  listen: TCPSourceListener tag,
  notify: TCPSourceNotify iso,
  routes: Array[Consumer tag] val,
  route_builder: RouteBuilder val,
  outgoing_boundary_builders: HashMap[String val, OutgoingBoundaryBuilder val, HashEq[String val] val] val,
  layout_initializer: LayoutInitializer tag,
  fd: U32 val,
  init_size: USize val = seq,
  max_size: USize val = seq,
  metrics_reporter: MetricsReporter iso,
  router_registry: RouterRegistry tag)
: TCPSource tag^
```
#### Parameters

*   listen: [TCPSourceListener](wallaroo-core-source-tcp_source-TCPSourceListener) tag
*   notify: [TCPSourceNotify](wallaroo-core-source-tcp_source-TCPSourceNotify) iso
*   routes: [Array](builtin-Array)\[[Consumer](wallaroo-core-common-Consumer) tag\] val
*   route_builder: [RouteBuilder](wallaroo-core-routing-RouteBuilder) val
*   outgoing_boundary_builders: [HashMap](collections-HashMap)\[[String](builtin-String) val, [OutgoingBoundaryBuilder](wallaroo-core-boundary-OutgoingBoundaryBuilder) val, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val
*   layout_initializer: [LayoutInitializer](wallaroo-core-initialization-LayoutInitializer) tag
*   fd: [U32](builtin-U32) val
*   init_size: [USize](builtin-USize) val = seq
*   max_size: [USize](builtin-USize) val = seq
*   metrics_reporter: [MetricsReporter](wallaroo-core-metrics-MetricsReporter) iso
*   router_registry: [RouterRegistry](wallaroo-ent-router_registry-RouterRegistry) tag

#### Returns

* [TCPSource](wallaroo-core-source-tcp_source-TCPSource) tag^

---

## Public Behaviours

### update_router

```pony
be update_router(
  router: Router val)
```
#### Parameters

*   router: [Router](wallaroo-core-topology-Router) val

---

### add_boundary_builders

Build a new boundary for each builder that corresponds to a worker we
don't yet have a boundary to. Each TCPSource has its own
OutgoingBoundary to each worker to allow for higher throughput.


```pony
be add_boundary_builders(
  boundary_builders: HashMap[String val, OutgoingBoundaryBuilder val, HashEq[String val] val] val)
```
#### Parameters

*   boundary_builders: [HashMap](collections-HashMap)\[[String](builtin-String) val, [OutgoingBoundaryBuilder](wallaroo-core-boundary-OutgoingBoundaryBuilder) val, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val

---

### remove_boundary

```pony
be remove_boundary(
  worker: String val)
```
#### Parameters

*   worker: [String](builtin-String) val

---

### reconnect_boundary

```pony
be reconnect_boundary(
  target_worker_name: String val)
```
#### Parameters

*   target_worker_name: [String](builtin-String) val

---

### remove_route_for

```pony
be remove_route_for(
  step: Consumer tag)
```
#### Parameters

*   step: [Consumer](wallaroo-core-common-Consumer) tag

---

### request_ack

```pony
be request_ack()
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

### dispose

- Close the connection gracefully.


```pony
be dispose()
```

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

## Public Functions

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

### close

Shut our connection down immediately. Stop reading data from the incoming
source.


```pony
fun ref close()
: None val
```

#### Returns

* [None](builtin-None) val

---

### is_muted

```pony
fun ref is_muted()
: Bool val
```

#### Returns

* [Bool](builtin-Bool) val

---

### expect

A `received` call on the notifier must contain exactly `qty` bytes. If
`qty` is zero, the call can contain any amount of data.


```pony
fun ref expect(
  qty: USize val = seq)
: None val
```
#### Parameters

*   qty: [USize](builtin-USize) val = seq

#### Returns

* [None](builtin-None) val

---

## Private Behaviours

### _event_notify

Handle socket events.


```pony
be _event_notify(
  event: Pointer[AsioEvent val] tag,
  flags: U32 val,
  arg: U32 val)
```
#### Parameters

*   event: [Pointer](builtin-Pointer)\[[AsioEvent](builtin-AsioEvent) val\] tag
*   flags: [U32](builtin-U32) val
*   arg: [U32](builtin-U32) val

---

### _read_again

Resume reading.


```pony
be _read_again()
```

---

## Private Functions

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

### _notify_connecting

Inform the notifier that we're connecting.


```pony
fun ref _notify_connecting()
: None val
```

#### Returns

* [None](builtin-None) val

---

### _try_shutdown

If we have closed and we have no remaining writes or pending connections,
then shutdown.


```pony
fun ref _try_shutdown()
: None val
```

#### Returns

* [None](builtin-None) val

---

### _hard_close

When an error happens, do a non-graceful close.


```pony
fun ref _hard_close()
: None val
```

#### Returns

* [None](builtin-None) val

---

### _dispose_routes

```pony
fun ref _dispose_routes()
: None val
```

#### Returns

* [None](builtin-None) val

---

### _pending_reads

Unless this connection is currently muted, read while data is available,
guessing the next packet length as we go. If we read 4 kb of data, send
ourself a resume message and stop reading, to avoid starving other actors.


```pony
fun ref _pending_reads()
: None val
```

#### Returns

* [None](builtin-None) val

---

### _read_buf_size

Resize the read buffer.


```pony
fun ref _read_buf_size(
  less: USize val)
: None val
```
#### Parameters

*   less: [USize](builtin-USize) val

#### Returns

* [None](builtin-None) val

---

### _mute

```pony
fun ref _mute()
: None val
```

#### Returns

* [None](builtin-None) val

---

### _unmute

```pony
fun ref _unmute()
: None val
```

#### Returns

* [None](builtin-None) val

---

