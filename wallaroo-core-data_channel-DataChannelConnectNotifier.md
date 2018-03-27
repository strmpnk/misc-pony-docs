# DataChannelConnectNotifier

```pony
class ref DataChannelConnectNotifier is
  DataChannelNotify ref
```

#### Implements

* [DataChannelNotify](wallaroo-core-data_channel-DataChannelNotify) ref

---

## Constructors

### create

```pony
new iso create(
  connections: Connections tag,
  auth: AmbientAuth val,
  metrics_reporter: MetricsReporter iso,
  layout_initializer: LayoutInitializer tag,
  data_receivers: DataReceivers tag,
  recovery_replayer: RecoveryReplayer tag,
  router_registry: RouterRegistry tag)
: DataChannelConnectNotifier iso^
```
#### Parameters

*   connections: [Connections](wallaroo-ent-network-Connections) tag
*   auth: [AmbientAuth](builtin-AmbientAuth) val
*   metrics_reporter: [MetricsReporter](wallaroo-core-metrics-MetricsReporter) iso
*   layout_initializer: [LayoutInitializer](wallaroo-core-initialization-LayoutInitializer) tag
*   data_receivers: [DataReceivers](wallaroo-ent-data_receiver-DataReceivers) tag
*   recovery_replayer: [RecoveryReplayer](wallaroo-ent-recovery-RecoveryReplayer) tag
*   router_registry: [RouterRegistry](wallaroo-ent-router_registry-RouterRegistry) tag

#### Returns

* [DataChannelConnectNotifier](wallaroo-core-data_channel-DataChannelConnectNotifier) iso^

---

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

### received

```pony
fun ref received(
  conn: DataChannel ref,
  data: Array[U8 val] iso,
  n: USize val)
: Bool val
```
#### Parameters

*   conn: [DataChannel](wallaroo-core-data_channel-DataChannel) ref
*   data: [Array](builtin-Array)\[[U8](builtin-U8) val\] iso
*   n: [USize](builtin-USize) val

#### Returns

* [Bool](builtin-Bool) val

---

### accepted

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

### connected

```pony
fun ref connected(
  sock: DataChannel ref)
: None val
```
#### Parameters

*   sock: [DataChannel](wallaroo-core-data_channel-DataChannel) ref

#### Returns

* [None](builtin-None) val

---

### closed

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

### connecting

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

### connect_failed

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

### expect

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

### throttled

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

