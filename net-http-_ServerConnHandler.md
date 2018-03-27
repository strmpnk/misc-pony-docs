# _ServerConnHandler

This is the network notification handler for the server. It uses
`PayloadBuilder` to assemble request `Payload` objects using received
chunks of data. Functions in this class execute within the
`TCPConnection` actor.


```pony
class ref _ServerConnHandler is
  TCPConnectionNotify ref
```

#### Implements

* [TCPConnectionNotify](net-TCPConnectionNotify) ref

---

## Constructors

### create

```pony
new iso create(
  handlermaker: HandlerFactory val,
  logger: Logger val,
  reversedns: (AmbientAuth val | NetAuth val | DNSAuth val | 
    None val),
  registry: HTTPServer tag)
: _ServerConnHandler iso^
```
#### Parameters

*   handlermaker: [HandlerFactory](net-http-HandlerFactory) val
*   logger: [Logger](net-http-Logger) val
*   reversedns: ([AmbientAuth](builtin-AmbientAuth) val | [NetAuth](net-NetAuth) val | [DNSAuth](net-DNSAuth) val | 
    [None](builtin-None) val)
*   registry: [HTTPServer](net-http-HTTPServer) tag

#### Returns

* [_ServerConnHandler](net-http-_ServerConnHandler) iso^

---

## Public Functions

### accepted

Accept the incoming TCP connection and create the actor that will
manage further communication, and the message parser that feeds it.


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

### received

Pass chunks of data to the `HTTPParser` for this session. It will
then pass completed information on the the `HTTPSession`.


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

### throttled

Notification that the TCP connection to the client can not accept data
for a while.


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

Notification that the TCP connection can resume accepting data.


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

### closed

The connection has been closed. Abort the session.


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

### connect_failed

The connect has failed. TODO: is it a case for server-side?


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

### connected

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

### auth_failed

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

