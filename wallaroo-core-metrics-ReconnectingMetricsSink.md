# ReconnectingMetricsSink

# MetricsSink

`MetricsSink` replaces the Pony standard library class `TCPConnection`
within Wallaroo for outgoing connections for metrics. While
`TCPConnection` offers a number of excellent features it doesn't
account for our needs around encoding of output messages in the sink.

`MetricsSink` is a copy of `TCPConnection` with
support for a behavior for sending metrics.


```pony
actor tag ReconnectingMetricsSink
```

## Constructors

### create

```pony
new tag create(
  host: String val,
  service: String val,
  application_name: String val,
  worker_name: String val,
  from: String val = seq,
  init_size: USize val = seq,
  max_size: USize val = seq,
  reconnect_pause: U64 val = seq)
: ReconnectingMetricsSink tag^
```
#### Parameters

*   host: [String](builtin-String) val
*   service: [String](builtin-String) val
*   application_name: [String](builtin-String) val
*   worker_name: [String](builtin-String) val
*   from: [String](builtin-String) val = seq
*   init_size: [USize](builtin-USize) val = seq
*   max_size: [USize](builtin-USize) val = seq
*   reconnect_pause: [U64](builtin-U64) val = seq

#### Returns

* [ReconnectingMetricsSink](wallaroo-core-metrics-ReconnectingMetricsSink) tag^

---

### ip4

```pony
new tag ip4(
  host: String val,
  service: String val,
  application_name: String val,
  worker_name: String val,
  from: String val = seq,
  init_size: USize val = seq,
  max_size: USize val = seq,
  reconnect_pause: U64 val = seq)
: ReconnectingMetricsSink tag^
```
#### Parameters

*   host: [String](builtin-String) val
*   service: [String](builtin-String) val
*   application_name: [String](builtin-String) val
*   worker_name: [String](builtin-String) val
*   from: [String](builtin-String) val = seq
*   init_size: [USize](builtin-USize) val = seq
*   max_size: [USize](builtin-USize) val = seq
*   reconnect_pause: [U64](builtin-U64) val = seq

#### Returns

* [ReconnectingMetricsSink](wallaroo-core-metrics-ReconnectingMetricsSink) tag^

---

### ip6

```pony
new tag ip6(
  host: String val,
  service: String val,
  application_name: String val,
  worker_name: String val,
  from: String val = seq,
  init_size: USize val = seq,
  max_size: USize val = seq,
  reconnect_pause: U64 val = seq)
: ReconnectingMetricsSink tag^
```
#### Parameters

*   host: [String](builtin-String) val
*   service: [String](builtin-String) val
*   application_name: [String](builtin-String) val
*   worker_name: [String](builtin-String) val
*   from: [String](builtin-String) val = seq
*   init_size: [USize](builtin-USize) val = seq
*   max_size: [USize](builtin-USize) val = seq
*   reconnect_pause: [U64](builtin-U64) val = seq

#### Returns

* [ReconnectingMetricsSink](wallaroo-core-metrics-ReconnectingMetricsSink) tag^

---

## Public Behaviours

### queue

Queue a single sequence of bytes on linux.
Do nothing on windows.


```pony
be queue(
  data: (String val | Array[U8 val] val))
```
#### Parameters

*   data: ([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)

---

### send_metrics

```pony
be send_metrics(
  metrics: Array[(String val , String val , String val , String val , U16 val , Histogram val , U64 val , U64 val , String val , String val)] val)
```
#### Parameters

*   metrics: [Array](builtin-Array)\[([String](builtin-String) val , [String](builtin-String) val , [String](builtin-String) val , [String](builtin-String) val , [U16](builtin-U16) val , [Histogram](wallaroo-core-metrics-Histogram) val , [U64](builtin-U64) val , [U64](builtin-U64) val , [String](builtin-String) val , [String](builtin-String) val)\] val

---

### writev

```pony
be writev(
  data: ByteSeqIter val)
```
#### Parameters

*   data: [ByteSeqIter](builtin-ByteSeqIter) val

---

### queuev

Queue a sequence of sequences of bytes on linux.
Do nothing on windows.


```pony
be queuev(
  data: ByteSeqIter val)
```
#### Parameters

*   data: [ByteSeqIter](builtin-ByteSeqIter) val

---

### send_queue

Write pending queue to network on linux.
Do nothing on windows.


```pony
be send_queue()
```

---

### mute

Temporarily suspend reading off this TCPConnection until such time as
`unmute` is called.


```pony
be mute()
```

---

### unmute

Start reading off this TCPConnection again after having been muted.


```pony
be unmute()
```

---

### set_notify

Change the notifier.


```pony
be set_notify(
  notify: MetricsSinkNotify iso)
```
#### Parameters

*   notify: [MetricsSinkNotify](wallaroo-core-metrics-MetricsSinkNotify) iso

---

### dispose

Close the connection gracefully once all writes are sent.


```pony
be dispose()
```

---

### reconnect

```pony
be reconnect()
```

---

## Public Functions

### local_address

Return the local IP address.


```pony
fun box local_address()
: NetAddress val
```

#### Returns

* [NetAddress](net-NetAddress) val

---

### remote_address

Return the remote IP address.


```pony
fun box remote_address()
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

### set_keepalive

Sets the TCP keepalive timeout to approximately secs seconds. Exact timing
is OS dependent. If secs is zero, TCP keepalive is disabled. TCP keepalive
is disabled by default. This can only be set on a connected socket.


```pony
fun ref set_keepalive(
  secs: U32 val)
: None val
```
#### Parameters

*   secs: [U32](builtin-U32) val

#### Returns

* [None](builtin-None) val

---

### write_final

Write as much as possible to the socket. Set _writeable to false if not
everything was written. On an error, close the connection. This is for
data that has already been transformed by the notifier.


```pony
fun ref write_final(
  data: (String val | Array[U8 val] val))
: None val
```
#### Parameters

*   data: ([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)

#### Returns

* [None](builtin-None) val

---

### close

Attempt to perform a graceful shutdown. Don't accept new writes. If the
connection isn't muted then we won't finish closing until we get a zero
length read.  If the connection is muted, perform a hard close and
shut down immediately.


```pony
fun ref close()
: None val
```

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

### _complete_writes

The OS has informed as that len bytes of pending writes have completed.
This occurs only with IOCP on Windows.


```pony
fun ref _complete_writes(
  len: U32 val)
: None val
```
#### Parameters

*   len: [U32](builtin-U32) val

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

### _complete_reads

The OS has informed as that len bytes of pending reads have completed.
This occurs only with IOCP on Windows.


```pony
fun ref _complete_reads(
  len: U32 val)
: None val
```
#### Parameters

*   len: [U32](builtin-U32) val

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

### _queue_read

Begin an IOCP read on Windows.


```pony
fun ref _queue_read()
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

### _notify_connecting

Inform the notifier that we're connecting.


```pony
fun ref _notify_connecting()
: None val
```

#### Returns

* [None](builtin-None) val

---

### _close

```pony
fun ref _close()
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

