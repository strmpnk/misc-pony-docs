# TCPSink

# TCPSink

`TCPSink` replaces the Pony standard library class `TCPConnection`
within Wallaroo for outgoing connections to external systems. While
`TCPConnection` offers a number of excellent features it doesn't
account for our needs around resilience.

`TCPSink` incorporates basic send/recv functionality from `TCPConnection` as
well working with our upstream backup/message acknowledgement system.

## Resilience and message tracking

...

## Possible future work

- Much better algo for determining how many credits to hand out per producer
- At the moment we treat sending over TCP as done. In the future we can and
  should support ack of the data being handled from the other side.
- Handle reconnecting after being disconnected from the downstream
- Optional in sink deduplication (this woud involve storing what we sent and
  was acknowleged.)


```pony
actor tag TCPSink is
  Consumer tag
```

#### Implements

* [Consumer](wallaroo-core-common-Consumer) tag

---

## Constructors

### create

```pony
new tag create(
  env: Env val,
  encoder_wrapper: TCPEncoderWrapper val,
  metrics_reporter: MetricsReporter iso,
  host: String val,
  service: String val,
  initial_msgs: Array[Array[(String val | Array[U8 val] val)] val] val,
  from: String val = seq,
  init_size: USize val = seq,
  max_size: USize val = seq,
  reconnect_pause: U64 val = seq)
: TCPSink tag^
```
#### Parameters

*   env: [Env](builtin-Env) val
*   encoder_wrapper: [TCPEncoderWrapper](wallaroo-core-sink-tcp_sink-TCPEncoderWrapper) val
*   metrics_reporter: [MetricsReporter](wallaroo-core-metrics-MetricsReporter) iso
*   host: [String](builtin-String) val
*   service: [String](builtin-String) val
*   initial_msgs: [Array](builtin-Array)\[[Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val\] val
*   from: [String](builtin-String) val = seq
*   init_size: [USize](builtin-USize) val = seq
*   max_size: [USize](builtin-USize) val = seq
*   reconnect_pause: [U64](builtin-U64) val = seq

#### Returns

* [TCPSink](wallaroo-core-sink-tcp_sink-TCPSink) tag^

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

### update_router

No-op: TCPSink has no router


```pony
be update_router(
  router: Router val)
```
#### Parameters

*   router: [Router](wallaroo-core-topology-Router) val

---

### receive_state

```pony
be receive_state(
  state: (String val | Array[U8 val] val))
```
#### Parameters

*   state: ([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)

---

### dispose

Gracefully shuts down the sink. Allows all pending writes
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

### reconnect

```pony
be reconnect()
```

---

## Public Functions

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

### local_address

Return the local IP address.


```pony
fun box local_address()
: NetAddress val
```

#### Returns

* [NetAddress](net-NetAddress) val

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

### receive_connect_ack

For WallarooOutgoingNetworkActor only.
This would be needed if we used a handshake to connect downstream.


```pony
fun ref receive_connect_ack(
  seq_id: U64 val)
: None val
```
#### Parameters

*   seq_id: [U64](builtin-U64) val

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

### receive_ack

For WallarooOutgoingNetworkActor only.
This would be needed if we start only acking once we receive some kind
of confirmation from the downstream.


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

### _initial_connect

```pony
fun ref _initial_connect()
: None val
```

#### Returns

* [None](builtin-None) val

---

### _next_tracking_id

```pony
fun ref _next_tracking_id(
  i_producer: Producer tag,
  i_route_id: U64 val,
  i_seq_id: U64 val)
: (U64 val | None val)
```
#### Parameters

*   i_producer: [Producer](wallaroo-core-common-Producer) tag
*   i_route_id: [U64](builtin-U64) val
*   i_seq_id: [U64](builtin-U64) val

#### Returns

* ([U64](builtin-U64) val | [None](builtin-None) val)

---

### _unit_finished

Handles book keeping related to resilience. Called when
a collection of sends is completed. When backpressure hasn't been applied,
this would be called for each send. When backpressure has been applied and
there is pending work to send, this would be called once after we finish
attempting to catch up on sending pending data.


```pony
fun ref _unit_finished(
  number_finished: ISize val,
  number_tracked_finished: ISize val,
  tracking_id: (U64 val | None val))
: None val
```
#### Parameters

*   number_finished: [ISize](builtin-ISize) val
*   number_tracked_finished: [ISize](builtin-ISize) val
*   tracking_id: ([U64](builtin-U64) val | [None](builtin-None) val)

#### Returns

* [None](builtin-None) val

---

### _writev

Write a sequence of sequences of bytes.


```pony
fun ref _writev(
  data: ByteSeqIter val,
  tracking_id: (U64 val | None val))
: None val
```
#### Parameters

*   data: [ByteSeqIter](builtin-ByteSeqIter) val
*   tracking_id: ([U64](builtin-U64) val | [None](builtin-None) val)

#### Returns

* [None](builtin-None) val

---

### _write_final

Write as much as possible to the socket. Set _writeable to false if not
everything was written. On an error, close the connection. This is for
data that has already been transformed by the notifier.


```pony
fun ref _write_final(
  data: (String val | Array[U8 val] val),
  tracking_id: (U64 val | None val))
: None val
```
#### Parameters

*   data: ([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)
*   tracking_id: ([U64](builtin-U64) val | [None](builtin-None) val)

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

### _tracking_finished

Call _unit_finished with:
  number of sent messages,
  number of tracked messages sent
  last tracking_id


```pony
fun ref _tracking_finished(
  num_bytes_sent: USize val)
: None val
```
#### Parameters

*   num_bytes_sent: [USize](builtin-USize) val

#### Returns

* [None](builtin-None) val

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

### _schedule_reconnect

```pony
fun ref _schedule_reconnect()
: None val
```

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

