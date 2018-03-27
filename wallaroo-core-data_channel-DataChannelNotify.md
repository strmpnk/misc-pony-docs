# DataChannelNotify

Notifications for DataChannel connections.

For an example of using this class please see the documentation for the
`DataChannel` and `DataChannelListener` actors.


```pony
interface ref DataChannelNotify
```

## Public Functions

### identify_data_receiver

Each abstract data channel (a connection from an OutgoingBoundary)
corresponds to a single DataReceiver. On reconnect, we want a new
DataChannel for that boundary to use the same DataReceiver. This is
called once we have found (or initially created) the DataReceiver for
the DataChannel corresponding to this notify.


```pony
fun ref identify_data_receiver(
  dr: DataReceiver tag,
  sender_boundary_id: U128 val,
  conn: DataChannel ref)
: None val
```
#### Parameters

*   dr: [DataReceiver](wallaroo-ent-data_receiver-DataReceiver) tag
*   sender_boundary_id: [U128](builtin-U128) val
*   conn: [DataChannel](wallaroo-core-data_channel-DataChannel) ref

#### Returns

* [None](builtin-None) val

---

### accepted

Called when a DataChannel is accepted by a DataChannelListener.


```pony
fun ref accepted(
  conn: DataChannel ref)
: None val
```
#### Parameters

*   conn: [DataChannel](wallaroo-core-data_channel-DataChannel) ref

#### Returns

* [None](builtin-None) val

---

### connecting

Called if name resolution succeeded for a DataChannel and we are now
waiting for a connection to the server to succeed. The count is the number
of connections we're trying. The notifier will be informed each time the
count changes, until a connection is made or connect_failed() is called.


```pony
fun ref connecting(
  conn: DataChannel ref,
  count: U32 val)
: None val
```
#### Parameters

*   conn: [DataChannel](wallaroo-core-data_channel-DataChannel) ref
*   count: [U32](builtin-U32) val

#### Returns

* [None](builtin-None) val

---

### connected

Called when we have successfully connected to the server.


```pony
fun ref connected(
  conn: DataChannel ref)
: None val
```
#### Parameters

*   conn: [DataChannel](wallaroo-core-data_channel-DataChannel) ref

#### Returns

* [None](builtin-None) val

---

### connect_failed

Called when we have failed to connect to all possible addresses for the
server. At this point, the connection will never be established.


```pony
fun ref connect_failed(
  conn: DataChannel ref)
: None val
```
#### Parameters

*   conn: [DataChannel](wallaroo-core-data_channel-DataChannel) ref

#### Returns

* [None](builtin-None) val

---

### auth_failed

A raw DataChannel has no authentication mechanism. However, when
protocols are wrapped in other protocols, this can be used to report an
authentication failure in a lower level protocol (e.g. SSL).


```pony
fun ref auth_failed(
  conn: DataChannel ref)
: None val
```
#### Parameters

*   conn: [DataChannel](wallaroo-core-data_channel-DataChannel) ref

#### Returns

* [None](builtin-None) val

---

### sent

Called when data is sent on the connection. This gives the notifier an
opportunity to modify sent data before it is written. To swallow data,
return an empty string.


```pony
fun ref sent(
  conn: DataChannel ref,
  data: (String val | Array[U8 val] val))
: (String val | Array[U8 val] val)
```
#### Parameters

*   conn: [DataChannel](wallaroo-core-data_channel-DataChannel) ref
*   data: ([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)

#### Returns

* ([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)

---

### sentv

Called when multiple chunks of data are sent to the connection in a single
call. This gives the notifier an opportunity to modify the sent data chunks
before they are written. To swallow the send, return an empty
Array[String].


```pony
fun ref sentv(
  conn: DataChannel ref,
  data: ByteSeqIter val)
: ByteSeqIter val
```
#### Parameters

*   conn: [DataChannel](wallaroo-core-data_channel-DataChannel) ref
*   data: [ByteSeqIter](builtin-ByteSeqIter) val

#### Returns

* [ByteSeqIter](builtin-ByteSeqIter) val

---

### received

Called when new data is received on the connection. Return true if you
want to continue receiving messages without yielding until you read
max_size on the DataChannel. Return false to cause the DataChannel
to yield now.

Includes the number of times during the current behavior, that received has
been called. This allows the notifier to end reads on a regular basis.


```pony
fun ref received(
  conn: DataChannel ref,
  data: Array[U8 val] iso,
  times: USize val)
: Bool val
```
#### Parameters

*   conn: [DataChannel](wallaroo-core-data_channel-DataChannel) ref
*   data: [Array](builtin-Array)\[[U8](builtin-U8) val\] iso
*   times: [USize](builtin-USize) val

#### Returns

* [Bool](builtin-Bool) val

---

### expect

Called when the connection has been told to expect a certain quantity of
bytes. This allows nested notifiers to change the expected quantity, which
allows a lower level protocol to handle any framing (e.g. SSL).


```pony
fun ref expect(
  conn: DataChannel ref,
  qty: USize val)
: USize val
```
#### Parameters

*   conn: [DataChannel](wallaroo-core-data_channel-DataChannel) ref
*   qty: [USize](builtin-USize) val

#### Returns

* [USize](builtin-USize) val

---

### closed

Called when the connection is closed.


```pony
fun ref closed(
  conn: DataChannel ref)
: None val
```
#### Parameters

*   conn: [DataChannel](wallaroo-core-data_channel-DataChannel) ref

#### Returns

* [None](builtin-None) val

---

### throttled

Called when the connection starts experiencing TCP backpressure. You should
respond to this by pausing additional calls to `write` and `writev` until
you are informed that pressure has been released. Failure to respond to
the `throttled` notification will result in outgoing data queuing in the
connection and increasing memory usage.


```pony
fun ref throttled(
  conn: DataChannel ref)
: None val
```
#### Parameters

*   conn: [DataChannel](wallaroo-core-data_channel-DataChannel) ref

#### Returns

* [None](builtin-None) val

---

### unthrottled

Called when the connection stops experiencing TCP backpressure. Upon
receiving this notification, you should feel free to start making calls to
`write` and `writev` again.


```pony
fun ref unthrottled(
  conn: DataChannel ref)
: None val
```
#### Parameters

*   conn: [DataChannel](wallaroo-core-data_channel-DataChannel) ref

#### Returns

* [None](builtin-None) val

---

