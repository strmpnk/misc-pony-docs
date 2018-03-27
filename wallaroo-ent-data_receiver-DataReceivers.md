# DataReceivers

```pony
actor tag DataReceivers
```

## Constructors

### create

```pony
new tag create(
  auth: AmbientAuth val,
  connections: Connections tag,
  worker_name: String val,
  is_recovering: Bool val = seq)
: DataReceivers tag^
```
#### Parameters

*   auth: [AmbientAuth](builtin-AmbientAuth) val
*   connections: [Connections](wallaroo-ent-network-Connections) tag
*   worker_name: [String](builtin-String) val
*   is_recovering: [Bool](builtin-Bool) val = seq

#### Returns

* [DataReceivers](wallaroo-ent-data_receiver-DataReceivers) tag^

---

## Public Behaviours

### subscribe

```pony
be subscribe(
  sub: DataReceiversSubscriber tag)
```
#### Parameters

*   sub: [DataReceiversSubscriber](wallaroo-ent-data_receiver-DataReceiversSubscriber) tag

---

### request_data_receiver

Called when a DataChannel is first created and needs to know the
DataReceiver corresponding to the relevant OutgoingBoundary. If this
is the first time that OutgoingBoundary has connected to this worker,
then we create a new DataReceiver here.


```pony
be request_data_receiver(
  sender_name: String val,
  sender_boundary_id: U128 val,
  conn: DataChannel tag)
```
#### Parameters

*   sender_name: [String](builtin-String) val
*   sender_boundary_id: [U128](builtin-U128) val
*   conn: [DataChannel](wallaroo-core-data_channel-DataChannel) tag

---

### start_replay_processing

```pony
be start_replay_processing()
```

---

### start_normal_message_processing

```pony
be start_normal_message_processing()
```

---

### update_data_router

```pony
be update_data_router(
  dr: DataRouter val)
```
#### Parameters

*   dr: [DataRouter](wallaroo-core-topology-DataRouter) val

---

## Private Functions

### _inform_subscribers

```pony
fun box _inform_subscribers(
  b_id: BoundaryId ref,
  dr: DataReceiver tag)
: None val
```
#### Parameters

*   b_id: [BoundaryId](wallaroo-core-common-BoundaryId) ref
*   dr: [DataReceiver](wallaroo-ent-data_receiver-DataReceiver) tag

#### Returns

* [None](builtin-None) val

---

