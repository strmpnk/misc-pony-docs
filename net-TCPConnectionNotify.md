# TCPConnectionNotify

Notifications for TCP connections.

For an example of using this class please see the documentation for the
`TCPConnection` and `TCPListener` actors.


```pony
interface ref TCPConnectionNotify
```

## Public Functions

### accepted

Called when a TCPConnection is accepted by a TCPListener.


```pony
fun ref accepted(
  conn: TCPConnection ref)
: None val
```
#### Parameters

*   conn: [TCPConnection](net-TCPConnection) ref

#### Returns

* [None](builtin-None) val

---

### connecting

Called if name resolution succeeded for a TCPConnection and we are now
waiting for a connection to the server to succeed. The count is the number
of connections we're trying. The notifier will be informed each time the
count changes, until a connection is made or connect_failed() is called.


```pony
fun ref connecting(
  conn: TCPConnection ref,
  count: U32 val)
: None val
```
#### Parameters

*   conn: [TCPConnection](net-TCPConnection) ref
*   count: [U32](builtin-U32) val

#### Returns

* [None](builtin-None) val

---

### connected

Called when we have successfully connected to the server.


```pony
fun ref connected(
  conn: TCPConnection ref)
: None val
```
#### Parameters

*   conn: [TCPConnection](net-TCPConnection) ref

#### Returns

* [None](builtin-None) val

---

### connect_failed

Called when we have failed to connect to all possible addresses for the
server. At this point, the connection will never be established.

It is expected to implement proper error handling. You need to opt in to
ignoring errors, which can be implemented like this:

```pony
fun ref connect_failed(conn: TCPConnection ref) =>
  None
```


```pony
fun ref connect_failed(
  conn: TCPConnection ref)
: None val
```
#### Parameters

*   conn: [TCPConnection](net-TCPConnection) ref

#### Returns

* [None](builtin-None) val

---

### auth_failed

A raw TCPConnection has no authentication mechanism. However, when
protocols are wrapped in other protocols, this can be used to report an
authentication failure in a lower level protocol (e.g. SSL).


```pony
fun ref auth_failed(
  conn: TCPConnection ref)
: None val
```
#### Parameters

*   conn: [TCPConnection](net-TCPConnection) ref

#### Returns

* [None](builtin-None) val

---

### sent

Called when data is sent on the connection. This gives the notifier an
opportunity to modify sent data before it is written. To swallow data,
return an empty string.


```pony
fun ref sent(
  conn: TCPConnection ref,
  data: (String val | Array[U8 val] val))
: (String val | Array[U8 val] val)
```
#### Parameters

*   conn: [TCPConnection](net-TCPConnection) ref
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
  conn: TCPConnection ref,
  data: ByteSeqIter val)
: ByteSeqIter val
```
#### Parameters

*   conn: [TCPConnection](net-TCPConnection) ref
*   data: [ByteSeqIter](builtin-ByteSeqIter) val

#### Returns

* [ByteSeqIter](builtin-ByteSeqIter) val

---

### received

Called when new data is received on the connection. Return true if you
want to continue receiving messages without yielding until you read
max_size on the TCPConnection. Return false to cause the TCPConnection
to yield now.

Includes the number of times during the current behavior, that received has
been called. This allows the notifier to end reads on a regular basis.


```pony
fun ref received(
  conn: TCPConnection ref,
  data: Array[U8 val] iso,
  times: USize val)
: Bool val
```
#### Parameters

*   conn: [TCPConnection](net-TCPConnection) ref
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
  conn: TCPConnection ref,
  qty: USize val)
: USize val
```
#### Parameters

*   conn: [TCPConnection](net-TCPConnection) ref
*   qty: [USize](builtin-USize) val

#### Returns

* [USize](builtin-USize) val

---

### closed

Called when the connection is closed.


```pony
fun ref closed(
  conn: TCPConnection ref)
: None val
```
#### Parameters

*   conn: [TCPConnection](net-TCPConnection) ref

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
  conn: TCPConnection ref)
: None val
```
#### Parameters

*   conn: [TCPConnection](net-TCPConnection) ref

#### Returns

* [None](builtin-None) val

---

### unthrottled

Called when the connection stops experiencing TCP backpressure. Upon
receiving this notification, you should feel free to start making calls to
`write` and `writev` again.


```pony
fun ref unthrottled(
  conn: TCPConnection ref)
: None val
```
#### Parameters

*   conn: [TCPConnection](net-TCPConnection) ref

#### Returns

* [None](builtin-None) val

---

