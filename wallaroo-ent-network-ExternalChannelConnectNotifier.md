# ExternalChannelConnectNotifier

```pony
class ref ExternalChannelConnectNotifier is
  TCPConnectionNotify ref
```

#### Implements

* [TCPConnectionNotify](net-TCPConnectionNotify) ref

---

## Constructors

### create

```pony
new iso create(
  name: String val,
  auth: AmbientAuth val,
  connections: Connections tag,
  recovery_file_cleaner: RecoveryFileCleaner tag,
  local_topology_initializer: LocalTopologyInitializer tag)
: ExternalChannelConnectNotifier iso^
```
#### Parameters

*   name: [String](builtin-String) val
*   auth: [AmbientAuth](builtin-AmbientAuth) val
*   connections: [Connections](wallaroo-ent-network-Connections) tag
*   recovery_file_cleaner: [RecoveryFileCleaner](wallaroo-core-common-RecoveryFileCleaner) tag
*   local_topology_initializer: [LocalTopologyInitializer](wallaroo-core-initialization-LocalTopologyInitializer) tag

#### Returns

* [ExternalChannelConnectNotifier](wallaroo-ent-network-ExternalChannelConnectNotifier) iso^

---

## Public Functions

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

### received

```pony
fun ref received(
  conn: TCPConnection ref,
  data: Array[U8 val] iso,
  n: USize val)
: Bool val
```
#### Parameters

*   conn: [TCPConnection](net-TCPConnection) ref
*   data: [Array](builtin-Array)\[[U8](builtin-U8) val\] iso
*   n: [USize](builtin-USize) val

#### Returns

* [Bool](builtin-Bool) val

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

### connect_failed

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

### closed

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

