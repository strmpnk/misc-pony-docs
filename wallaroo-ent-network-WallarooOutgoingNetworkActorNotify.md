# WallarooOutgoingNetworkActorNotify

```pony
trait ref WallarooOutgoingNetworkActorNotify
```

## Public Functions

### connecting

Called if name resolution succeeded for a WallarooOutgoingNetworkActor
and we are now waiting for a connection to the server to succeed. The
count is the number of connections we're trying. The notifier will be
informed each time the count changes, until a connection is made or
connect_failed() is called.


```pony
fun ref connecting(
  conn: WallarooOutgoingNetworkActor ref,
  count: U32 val)
: None val
```
#### Parameters

*   conn: [WallarooOutgoingNetworkActor](wallaroo-ent-network-WallarooOutgoingNetworkActor) ref
*   count: [U32](builtin-U32) val

#### Returns

* [None](builtin-None) val

---

### connected

Called when we have successfully connected to the server.


```pony
fun ref connected(
  conn: WallarooOutgoingNetworkActor ref)
: None val
```
#### Parameters

*   conn: [WallarooOutgoingNetworkActor](wallaroo-ent-network-WallarooOutgoingNetworkActor) ref

#### Returns

* [None](builtin-None) val

---

### connect_failed

Called when we have failed to connect to all possible addresses for the
server. At this point, the connection will never be established.


```pony
fun ref connect_failed(
  conn: WallarooOutgoingNetworkActor ref)
: None val
```
#### Parameters

*   conn: [WallarooOutgoingNetworkActor](wallaroo-ent-network-WallarooOutgoingNetworkActor) ref

#### Returns

* [None](builtin-None) val

---

### closed

Called when the connection is closed.


```pony
fun ref closed(
  conn: WallarooOutgoingNetworkActor ref)
: None val
```
#### Parameters

*   conn: [WallarooOutgoingNetworkActor](wallaroo-ent-network-WallarooOutgoingNetworkActor) ref

#### Returns

* [None](builtin-None) val

---

### sentv

Called when multiple chunks of data are sent to the connection in a single
call. This gives the notifier an opportunity to modify the sent data chunks
before they are written. To swallow the send, return an empty
Array[String].


```pony
fun ref sentv(
  conn: WallarooOutgoingNetworkActor ref,
  data: ByteSeqIter val)
: ByteSeqIter val
```
#### Parameters

*   conn: [WallarooOutgoingNetworkActor](wallaroo-ent-network-WallarooOutgoingNetworkActor) ref
*   data: [ByteSeqIter](builtin-ByteSeqIter) val

#### Returns

* [ByteSeqIter](builtin-ByteSeqIter) val

---

### received

Called when new data is received on the connection. Return true if you
want to continue receiving messages without yielding until you read
max_size on the WallarooOutgoingNetworkActorNotify.  Return false to
cause the WallarooOutgoingNetworkActorNotify to yield now.

`times` parameter is the number of times this method has been called during
this behavior. Starts at 1.


```pony
fun ref received(
  conn: WallarooOutgoingNetworkActor ref,
  data: Array[U8 val] iso,
  times: USize val)
: Bool val
```
#### Parameters

*   conn: [WallarooOutgoingNetworkActor](wallaroo-ent-network-WallarooOutgoingNetworkActor) ref
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
  conn: WallarooOutgoingNetworkActor ref,
  qty: USize val)
: USize val
```
#### Parameters

*   conn: [WallarooOutgoingNetworkActor](wallaroo-ent-network-WallarooOutgoingNetworkActor) ref
*   qty: [USize](builtin-USize) val

#### Returns

* [USize](builtin-USize) val

---

### throttled

Called when the connection starts experiencing TCP backpressure. You should
respond to this by pausing additional calls to `write` and `writev` until
you are informed that pressure has been released. Failure to respond to
the `throttled` notification will result in outgoing data queuing in the
connection and increasing memory usage.


```pony
fun ref throttled(
  conn: WallarooOutgoingNetworkActor ref)
: None val
```
#### Parameters

*   conn: [WallarooOutgoingNetworkActor](wallaroo-ent-network-WallarooOutgoingNetworkActor) ref

#### Returns

* [None](builtin-None) val

---

### unthrottled

Called when the connection stops experiencing TCP backpressure. Upon
receiving this notification, you should feel free to start making calls to
`write` and `writev` again.


```pony
fun ref unthrottled(
  conn: WallarooOutgoingNetworkActor ref)
: None val
```
#### Parameters

*   conn: [WallarooOutgoingNetworkActor](wallaroo-ent-network-WallarooOutgoingNetworkActor) ref

#### Returns

* [None](builtin-None) val

---

### dispose

Called when the parent actor's dispose is called.


```pony
fun ref dispose()
: None val
```

#### Returns

* [None](builtin-None) val

---

