# DataChannel

```pony
actor tag DataChannel
```

## Constructors

### create

```pony
new tag create(
  auth: (AmbientAuth val | NetAuth val | TCPAuth val | 
    TCPConnectAuth val),
  notify: DataChannelNotify iso,
  host: String val,
  service: String val,
  from: String val = seq,
  init_size: USize val = seq,
  max_size: USize val = seq)
: DataChannel tag^
```
#### Parameters

*   auth: ([AmbientAuth](builtin-AmbientAuth) val | [NetAuth](net-NetAuth) val | [TCPAuth](net-TCPAuth) val | 
    [TCPConnectAuth](net-TCPConnectAuth) val)
*   notify: [DataChannelNotify](wallaroo-core-data_channel-DataChannelNotify) iso
*   host: [String](builtin-String) val
*   service: [String](builtin-String) val
*   from: [String](builtin-String) val = seq
*   init_size: [USize](builtin-USize) val = seq
*   max_size: [USize](builtin-USize) val = seq

#### Returns

* [DataChannel](wallaroo-core-data_channel-DataChannel) tag^

---

### ip4

```pony
new tag ip4(
  auth: (AmbientAuth val | NetAuth val | TCPAuth val | 
    TCPConnectAuth val),
  notify: DataChannelNotify iso,
  host: String val,
  service: String val,
  from: String val = seq,
  init_size: USize val = seq,
  max_size: USize val = seq)
: DataChannel tag^
```
#### Parameters

*   auth: ([AmbientAuth](builtin-AmbientAuth) val | [NetAuth](net-NetAuth) val | [TCPAuth](net-TCPAuth) val | 
    [TCPConnectAuth](net-TCPConnectAuth) val)
*   notify: [DataChannelNotify](wallaroo-core-data_channel-DataChannelNotify) iso
*   host: [String](builtin-String) val
*   service: [String](builtin-String) val
*   from: [String](builtin-String) val = seq
*   init_size: [USize](builtin-USize) val = seq
*   max_size: [USize](builtin-USize) val = seq

#### Returns

* [DataChannel](wallaroo-core-data_channel-DataChannel) tag^

---

### ip6

```pony
new tag ip6(
  auth: (AmbientAuth val | NetAuth val | TCPAuth val | 
    TCPConnectAuth val),
  notify: DataChannelNotify iso,
  host: String val,
  service: String val,
  from: String val = seq,
  init_size: USize val = seq,
  max_size: USize val = seq)
: DataChannel tag^
```
#### Parameters

*   auth: ([AmbientAuth](builtin-AmbientAuth) val | [NetAuth](net-NetAuth) val | [TCPAuth](net-TCPAuth) val | 
    [TCPConnectAuth](net-TCPConnectAuth) val)
*   notify: [DataChannelNotify](wallaroo-core-data_channel-DataChannelNotify) iso
*   host: [String](builtin-String) val
*   service: [String](builtin-String) val
*   from: [String](builtin-String) val = seq
*   init_size: [USize](builtin-USize) val = seq
*   max_size: [USize](builtin-USize) val = seq

#### Returns

* [DataChannel](wallaroo-core-data_channel-DataChannel) tag^

---

### _accept

```pony
new tag _accept(
  listen: DataChannelListener tag,
  notify: DataChannelNotify iso,
  fd: U32 val,
  init_size: USize val = seq,
  max_size: USize val = seq)
: DataChannel tag^
```
#### Parameters

*   listen: [DataChannelListener](wallaroo-core-data_channel-DataChannelListener) tag
*   notify: [DataChannelNotify](wallaroo-core-data_channel-DataChannelNotify) iso
*   fd: [U32](builtin-U32) val
*   init_size: [USize](builtin-USize) val = seq
*   max_size: [USize](builtin-USize) val = seq

#### Returns

* [DataChannel](wallaroo-core-data_channel-DataChannel) tag^

---

## Public Behaviours

### identify_data_receiver

Each abstract data channel (a connection from an OutgoingBoundary)
corresponds to a single DataReceiver. On reconnect, we want a new
DataChannel for that boundary to use the same DataReceiver. This is
called once we have found (or initially created) the DataReceiver for
this DataChannel.


```pony
be identify_data_receiver(
  dr: DataReceiver tag,
  sender_step_id: U128 val)
```
#### Parameters

*   dr: [DataReceiver](wallaroo-ent-data_receiver-DataReceiver) tag
*   sender_step_id: [U128](builtin-U128) val

---

### write

Write a single sequence of bytes.


```pony
be write(
  data: (String val | Array[U8 val] val))
```
#### Parameters

*   data: ([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)

---

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

Temporarily suspend reading off this DataChannel until such time as
`unmute` is called.


```pony
be mute(
  d: Any tag)
```
#### Parameters

*   d: [Any](builtin-Any) tag

---

### unmute

Start reading off this DataChannel again after having been muted.


```pony
be unmute(
  d: Any tag)
```
#### Parameters

*   d: [Any](builtin-Any) tag

---

### set_notify

Change the notifier.


```pony
be set_notify(
  notify: DataChannelNotify iso)
```
#### Parameters

*   notify: [DataChannelNotify](wallaroo-core-data_channel-DataChannelNotify) iso

---

### dispose

Close the connection gracefully once all writes are sent.


```pony
be dispose()
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

Shut our connection down immediately. Stop reading data from the incoming
source.


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

### _mute

```pony
fun ref _mute(
  d: Any tag)
: None val
```
#### Parameters

*   d: [Any](builtin-Any) tag

#### Returns

* [None](builtin-None) val

---

### _unmute

```pony
fun ref _unmute(
  d: Any tag)
: None val
```
#### Parameters

*   d: [Any](builtin-Any) tag

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

