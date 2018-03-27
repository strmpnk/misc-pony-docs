# UnthrottledNotify

```pony
class ref UnthrottledNotify is
  WallarooOutgoingNetworkActorNotify ref
```

#### Implements

* [WallarooOutgoingNetworkActorNotify](wallaroo-ent-network-WallarooOutgoingNetworkActorNotify) ref

---

## Constructors

### create

```pony
new iso create(
  h: TestHelper val,
  conn: WallarooOutgoingNetworkActor tag)
: UnthrottledNotify iso^
```
#### Parameters

*   h: [TestHelper](ponytest-TestHelper) val
*   conn: [WallarooOutgoingNetworkActor](wallaroo-ent-network-WallarooOutgoingNetworkActor) tag

#### Returns

* [UnthrottledNotify](wallaroo-ent-spike-UnthrottledNotify) iso^

---

## Public Functions

### connecting

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

```pony
fun ref dispose()
: None val
```

#### Returns

* [None](builtin-None) val

---

