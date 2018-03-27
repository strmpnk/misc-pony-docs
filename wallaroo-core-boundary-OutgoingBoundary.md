# OutgoingBoundary

```pony
actor tag OutgoingBoundary is
  Consumer tag
```

#### Implements

* [Consumer](wallaroo-core-common-Consumer) tag

---

## Constructors

### create

```pony
new tag create(
  auth: AmbientAuth val,
  worker_name: String val,
  metrics_reporter: MetricsReporter iso,
  host: String val,
  service: String val,
  from: String val = seq,
  init_size: USize val = seq,
  max_size: USize val = seq,
  spike_config: (SpikeConfig val | None val) = seq)
: OutgoingBoundary tag^
```
#### Parameters

*   auth: [AmbientAuth](builtin-AmbientAuth) val
*   worker_name: [String](builtin-String) val
*   metrics_reporter: [MetricsReporter](wallaroo-core-metrics-MetricsReporter) iso
*   host: [String](builtin-String) val
*   service: [String](builtin-String) val
*   from: [String](builtin-String) val = seq
*   init_size: [USize](builtin-USize) val = seq
*   max_size: [USize](builtin-USize) val = seq
*   spike_config: ([SpikeConfig](wallaroo-ent-spike-SpikeConfig) val | [None](builtin-None) val) = seq

#### Returns

* [OutgoingBoundary](wallaroo-core-boundary-OutgoingBoundary) tag^

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

### quick_initialize

Called when initializing as part of a new worker joining a running cluster.


```pony
be quick_initialize(
  initializer: LayoutInitializer tag)
```
#### Parameters

*   initializer: [LayoutInitializer](wallaroo-core-initialization-LayoutInitializer) tag

---

### reconnect

```pony
be reconnect()
```

---

### migrate_step\[K: ([Hashable](collections-Hashable) val & [Equatable](builtin-Equatable)\[K\] val)\]

```pony
be migrate_step[K: (Hashable val & Equatable[K] val)](
  step_id: U128 val,
  state_name: String val,
  key: K,
  state: (String val | Array[U8 val] val))
```
#### Parameters

*   step_id: [U128](builtin-U128) val
*   state_name: [String](builtin-String) val
*   key: K
*   state: ([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)

---

### send_migration_batch_complete

```pony
be send_migration_batch_complete()
```

---

### register_step_id

```pony
be register_step_id(
  step_id: U128 val)
```
#### Parameters

*   step_id: [U128](builtin-U128) val

---

### run\[D: [Any](builtin-Any) val\]

```pony
be run[D: Any val](
  metric_name: String val,
  pipeline_time_spent: U64 val,
  data: D,
  producer: Producer tag,
  msg_uid: U128 val,
  frac_ids: (Array[U32 val] val | None val),
  seq_id: U64 val,
  route_id: U64 val,
  latest_ts: U64 val,
  metrics_id: U16 val,
  worker_ingress_ts: U64 val)
```
#### Parameters

*   metric_name: [String](builtin-String) val
*   pipeline_time_spent: [U64](builtin-U64) val
*   data: D
*   producer: [Producer](wallaroo-core-common-Producer) tag
*   msg_uid: [U128](builtin-U128) val
*   frac_ids: ([Array](builtin-Array)\[[U32](builtin-U32) val\] val | [None](builtin-None) val)
*   seq_id: [U64](builtin-U64) val
*   route_id: [U64](builtin-U64) val
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
  producer: Producer tag,
  msg_uid: U128 val,
  frac_ids: (Array[U32 val] val | None val),
  incoming_seq_id: U64 val,
  route_id: U64 val,
  latest_ts: U64 val,
  metrics_id: U16 val,
  worker_ingress_ts: U64 val)
```
#### Parameters

*   metric_name: [String](builtin-String) val
*   pipeline_time_spent: [U64](builtin-U64) val
*   data: D
*   producer: [Producer](wallaroo-core-common-Producer) tag
*   msg_uid: [U128](builtin-U128) val
*   frac_ids: ([Array](builtin-Array)\[[U32](builtin-U32) val\] val | [None](builtin-None) val)
*   incoming_seq_id: [U64](builtin-U64) val
*   route_id: [U64](builtin-U64) val
*   latest_ts: [U64](builtin-U64) val
*   metrics_id: [U16](builtin-U16) val
*   worker_ingress_ts: [U64](builtin-U64) val

---

### forward

```pony
be forward(
  delivery_msg: ReplayableDeliveryMsg val,
  pipeline_time_spent: U64 val,
  i_producer: Producer tag,
  i_seq_id: U64 val,
  i_route_id: U64 val,
  latest_ts: U64 val,
  metrics_id: U16 val,
  worker_ingress_ts: U64 val)
```
#### Parameters

*   delivery_msg: [ReplayableDeliveryMsg](wallaroo-core-messages-ReplayableDeliveryMsg) val
*   pipeline_time_spent: [U64](builtin-U64) val
*   i_producer: [Producer](wallaroo-core-common-Producer) tag
*   i_seq_id: [U64](builtin-U64) val
*   i_route_id: [U64](builtin-U64) val
*   latest_ts: [U64](builtin-U64) val
*   metrics_id: [U16](builtin-U16) val
*   worker_ingress_ts: [U64](builtin-U64) val

---

### writev

```pony
be writev(
  data: Array[(String val | Array[U8 val] val)] val)
```
#### Parameters

*   data: [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val

---

### receive_state

```pony
be receive_state(
  state: (String val | Array[U8 val] val))
```
#### Parameters

*   state: ([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)

---

### update_router

No-op: OutgoingBoundary has no router


```pony
be update_router(
  router: Router val)
```
#### Parameters

*   router: [Router](wallaroo-core-topology-Router) val

---

### dispose

Gracefully shuts down the outgoing boundary. Allows all pending writes
to be sent but any writes that arrive after this will be
silently discarded and not acknowleged.


```pony
be dispose()
```

---

### request_ack

```pony
be request_ack()
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

## Public Functions

### receive_ack

```pony
fun ref receive_ack(
  seq_id: U64 val)
: None val
```
#### Parameters

*   seq_id: [U64](builtin-U64) val

#### Returns

* [None](builtin-None) val

---

### receive_connect_ack

```pony
fun ref receive_connect_ack(
  last_id_seen: U64 val)
: None val
```
#### Parameters

*   last_id_seen: [U64](builtin-U64) val

#### Returns

* [None](builtin-None) val

---

### start_normal_sending

```pony
fun ref start_normal_sending()
: None val
```

#### Returns

* [None](builtin-None) val

---

### close

Perform a graceful shutdown. Don't accept new writes, but don't finish
closing until we get a zero length read.


```pony
fun ref close()
: None val
```

#### Returns

* [None](builtin-None) val

---

### expect

A `received` call on the notifier must contain exactly `qty` bytes. If
`qty` is zero, the call can contain any amount of data. This has no effect
if called in the `sent` notifier callback.


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

### local_address

Return the local IP address.


```pony
fun box local_address()
: NetAddress val
```

#### Returns

* [NetAddress](net-NetAddress) val

---

### set_nodelay

Turn Nagle on/off. Defaults to on. This can only be set on a connected
socket.


```pony
fun ref set_nodelay(
  state: Bool val)
: None val
```
#### Parameters

*   state: [Bool](builtin-Bool) val

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

### _replay_from

```pony
fun ref _replay_from(
  idx: U64 val)
: None val
```
#### Parameters

*   idx: [U64](builtin-U64) val

#### Returns

* [None](builtin-None) val

---

### _on_connected

```pony
fun ref _on_connected()
: None val
```

#### Returns

* [None](builtin-None) val

---

### _schedule_reconnect

```pony
fun ref _schedule_reconnect()
: None val
```

#### Returns

* [None](builtin-None) val

---

### _writev

Write a sequence of sequences of bytes.


```pony
fun ref _writev(
  data: ByteSeqIter val)
: None val
```
#### Parameters

*   data: [ByteSeqIter](builtin-ByteSeqIter) val

#### Returns

* [None](builtin-None) val

---

### _write_final

Write as much as possible to the socket. Set _writeable to false if not
everything was written. On an error, close the connection. This is for
data that has already been transformed by the notifier.


```pony
fun ref _write_final(
  data: (String val | Array[U8 val] val))
: None val
```
#### Parameters

*   data: ([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)

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

### _pending_writes

Send pending data. If any data can't be sent, keep it and mark as not
writeable. On an error, dispose of the connection. Returns whether
it sent all pending data or not.


```pony
fun ref _pending_writes()
: Bool val
```

#### Returns

* [Bool](builtin-Bool) val

---

### _read_buf_size

Resize the read buffer.


```pony
fun ref _read_buf_size()
: None val
```

#### Returns

* [None](builtin-None) val

---

### _add_to_upstream_backup

```pony
fun ref _add_to_upstream_backup(
  msg: Array[(String val | Array[U8 val] val)] val)
: None val
```
#### Parameters

*   msg: [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val

#### Returns

* [None](builtin-None) val

---

### _apply_backpressure

```pony
fun ref _apply_backpressure()
: None val
```

#### Returns

* [None](builtin-None) val

---

### _release_backpressure

```pony
fun ref _release_backpressure()
: None val
```

#### Returns

* [None](builtin-None) val

---

### _maybe_mute_or_unmute_upstreams

```pony
fun ref _maybe_mute_or_unmute_upstreams()
: None val
```

#### Returns

* [None](builtin-None) val

---

### _mute_upstreams

```pony
fun ref _mute_upstreams()
: None val
```

#### Returns

* [None](builtin-None) val

---

### _unmute_upstreams

```pony
fun ref _unmute_upstreams()
: None val
```

#### Returns

* [None](builtin-None) val

---

### _can_send

```pony
fun box _can_send()
: Bool val
```

#### Returns

* [Bool](builtin-Bool) val

---

### _backup_queue_is_overflowing

```pony
fun box _backup_queue_is_overflowing()
: Bool val
```

#### Returns

* [Bool](builtin-Bool) val

---

