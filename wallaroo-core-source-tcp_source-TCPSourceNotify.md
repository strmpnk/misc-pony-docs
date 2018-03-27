# TCPSourceNotify

```pony
interface ref TCPSourceNotify
```

## Public Functions

### routes

```pony
fun ref routes()
: Array[Consumer tag] val
```

#### Returns

* [Array](builtin-Array)\[[Consumer](wallaroo-core-common-Consumer) tag\] val

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

Called when a TCPSource is accepted by a TCPSourceListener.


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

### connecting

Called if name resolution succeeded for a TCPSource and we are now
waiting for a connection to the server to succeed. The count is the number
of connections we're trying. The notifier will be informed each time the
count changes, until a connection is made or connect_failed() is called.


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

Called when we have successfully connected to the server.


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

Called when we have failed to connect to all possible addresses for the
server. At this point, the connection will never be established.


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

### received

Called when new data is received on the connection. Return true if you
want to continue receiving messages without yielding until you read
max_size on the TCPSource.  Return false to cause the TCPSource
to yield now.


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

### expect

Called when the connection has been told to expect a certain quantity of
bytes. This allows nested notifiers to change the expected quantity, which
allows a lower level protocol to handle any framing (e.g. SSL).


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

### closed

Called when the connection is closed.


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

