# _ClientConnHandler

This is the network notification handler for the client. It passes
received data to the `HTTPParser` to assemble response `Payload` objects.


```pony
class ref _ClientConnHandler is
  TCPConnectionNotify ref
```

#### Implements

* [TCPConnectionNotify](net-TCPConnectionNotify) ref

---

## Constructors

### create

```pony
new iso create(
  client: _ClientConnection tag)
: _ClientConnHandler iso^
```
#### Parameters

*   client: [_ClientConnection](net-http-_ClientConnection) tag

#### Returns

* [_ClientConnHandler](net-http-_ClientConnHandler) iso^

---

## Public Functions

### connected

Tell the client we have connected.


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

The connection could not be established. Tell the client not to proceed.


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

SSL authentication failed. Tell the client not to proceed.


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

### received

Pass a received chunk of data to the `_HTTPParser`.


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

### closed

The connection has closed, possibly prematurely.


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

TCP connection wants us to stop sending. We do not do anything with
this here;  just pass it on to the `HTTPSession`.


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

### unthrottle

TCP can accept more data now. We just pass this on to the
`HTTPSession`


```pony
fun ref unthrottle(
  conn: TCPConnection ref)
: None val
```
#### Parameters

*   conn: [TCPConnection](net-TCPConnection) ref

#### Returns

* [None](builtin-None) val

---

### accepted

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

### sent

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

### expect

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

### unthrottled

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

