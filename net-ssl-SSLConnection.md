# SSLConnection

Wrap another protocol in an SSL connection.


```pony
class ref SSLConnection is
  TCPConnectionNotify ref
```

#### Implements

* [TCPConnectionNotify](net-TCPConnectionNotify) ref

---

## Constructors

### create

```pony
new iso create(
  notify: TCPConnectionNotify iso,
  ssl: SSL iso)
: SSLConnection iso^
```
#### Parameters

*   notify: [TCPConnectionNotify](net-TCPConnectionNotify) iso
*   ssl: [SSL](net-ssl-SSL) iso

#### Returns

* [SSLConnection](net-ssl-SSLConnection) iso^

---

## Public Functions

### accepted

Forward to the wrapped protocol.


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

Forward to the wrapped protocol.


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

Swallow this event until the handshake is complete.


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

Forward to the wrapped protocol.


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

### sent

Pass the data to the SSL session and check for both new application data
and new destination data.


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

### received

Pass the data to the SSL session and check for both new application data
and new destination data.


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

Keep track of the expect count for the wrapped protocol. Always tell the
TCPConnection to read all available data.


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

Forward to the wrapped protocol.


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

### throttled

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

## Private Functions

### _poll

Checks for both new application data and new destination data. Informs the
wrapped protocol that is has connected when the handshake is complete.


```pony
fun ref _poll(
  conn: TCPConnection ref)
: None val
```
#### Parameters

*   conn: [TCPConnection](net-TCPConnection) ref

#### Returns

* [None](builtin-None) val

---

