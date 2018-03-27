# DataRouter

```pony
class val DataRouter is
  Equatable[DataRouter val] ref
```

#### Implements

* [Equatable](builtin-Equatable)\[[DataRouter](wallaroo-core-topology-DataRouter) val\] ref

---

## Constructors

### create

```pony
new val create(
  data_routes: HashMap[U128 val, Consumer tag, HashEq[U128 val] val] val = seq)
: DataRouter val^
```
#### Parameters

*   data_routes: [HashMap](collections-HashMap)\[[U128](builtin-U128) val, [Consumer](wallaroo-core-common-Consumer) tag, [HashEq](collections-HashEq)\[[U128](builtin-U128) val\] val\] val = seq

#### Returns

* [DataRouter](wallaroo-core-topology-DataRouter) val^

---

### with_route_ids

```pony
new val with_route_ids(
  data_routes: HashMap[U128 val, Consumer tag, HashEq[U128 val] val] val,
  target_ids_to_route_ids: HashMap[U128 val, U64 val, HashEq[U128 val] val] val,
  route_ids_to_target_ids: HashMap[U64 val, U128 val, HashEq[U64 val] val] val)
: DataRouter val^
```
#### Parameters

*   data_routes: [HashMap](collections-HashMap)\[[U128](builtin-U128) val, [Consumer](wallaroo-core-common-Consumer) tag, [HashEq](collections-HashEq)\[[U128](builtin-U128) val\] val\] val
*   target_ids_to_route_ids: [HashMap](collections-HashMap)\[[U128](builtin-U128) val, [U64](builtin-U64) val, [HashEq](collections-HashEq)\[[U128](builtin-U128) val\] val\] val
*   route_ids_to_target_ids: [HashMap](collections-HashMap)\[[U64](builtin-U64) val, [U128](builtin-U128) val, [HashEq](collections-HashEq)\[[U64](builtin-U64) val\] val\] val

#### Returns

* [DataRouter](wallaroo-core-topology-DataRouter) val^

---

## Public Functions

### step_for_id

```pony
fun box step_for_id(
  id: U128 val)
: Consumer tag ?
```
#### Parameters

*   id: [U128](builtin-U128) val

#### Returns

* [Consumer](wallaroo-core-common-Consumer) tag ?

---

### route

```pony
fun box route(
  d_msg: DeliveryMsg val,
  pipeline_time_spent: U64 val,
  producer: DataReceiver ref,
  seq_id: U64 val,
  latest_ts: U64 val,
  metrics_id: U16 val,
  worker_ingress_ts: U64 val)
: None val
```
#### Parameters

*   d_msg: [DeliveryMsg](wallaroo-core-messages-DeliveryMsg) val
*   pipeline_time_spent: [U64](builtin-U64) val
*   producer: [DataReceiver](wallaroo-ent-data_receiver-DataReceiver) ref
*   seq_id: [U64](builtin-U64) val
*   latest_ts: [U64](builtin-U64) val
*   metrics_id: [U16](builtin-U16) val
*   worker_ingress_ts: [U64](builtin-U64) val

#### Returns

* [None](builtin-None) val

---

### replay_route

```pony
fun box replay_route(
  r_msg: ReplayableDeliveryMsg val,
  pipeline_time_spent: U64 val,
  producer: DataReceiver ref,
  seq_id: U64 val,
  latest_ts: U64 val,
  metrics_id: U16 val,
  worker_ingress_ts: U64 val)
: None val
```
#### Parameters

*   r_msg: [ReplayableDeliveryMsg](wallaroo-core-messages-ReplayableDeliveryMsg) val
*   pipeline_time_spent: [U64](builtin-U64) val
*   producer: [DataReceiver](wallaroo-ent-data_receiver-DataReceiver) ref
*   seq_id: [U64](builtin-U64) val
*   latest_ts: [U64](builtin-U64) val
*   metrics_id: [U16](builtin-U16) val
*   worker_ingress_ts: [U64](builtin-U64) val

#### Returns

* [None](builtin-None) val

---

### register_producer

```pony
fun box register_producer(
  producer: Producer tag)
: None val
```
#### Parameters

*   producer: [Producer](wallaroo-core-common-Producer) tag

#### Returns

* [None](builtin-None) val

---

### unregister_producer

```pony
fun box unregister_producer(
  producer: Producer tag)
: None val
```
#### Parameters

*   producer: [Producer](wallaroo-core-common-Producer) tag

#### Returns

* [None](builtin-None) val

---

### request_ack

```pony
fun box request_ack(
  r_ids: Array[U64 val] ref)
: None val
```
#### Parameters

*   r_ids: [Array](builtin-Array)\[[U64](builtin-U64) val\] ref

#### Returns

* [None](builtin-None) val

---

### route_ids

```pony
fun box route_ids()
: Array[U64 val] ref
```

#### Returns

* [Array](builtin-Array)\[[U64](builtin-U64) val\] ref

---

### routes

```pony
fun box routes()
: Array[Consumer tag] val
```

#### Returns

* [Array](builtin-Array)\[[Consumer](wallaroo-core-common-Consumer) tag\] val

---

### remove_route

```pony
fun box remove_route(
  id: U128 val)
: DataRouter val
```
#### Parameters

*   id: [U128](builtin-U128) val

#### Returns

* [DataRouter](wallaroo-core-topology-DataRouter) val

---

### add_route

```pony
fun box add_route(
  id: U128 val,
  target: Consumer tag)
: DataRouter val
```
#### Parameters

*   id: [U128](builtin-U128) val
*   target: [Consumer](wallaroo-core-common-Consumer) tag

#### Returns

* [DataRouter](wallaroo-core-topology-DataRouter) val

---

### eq

```pony
fun box eq(
  that: DataRouter val)
: Bool val
```
#### Parameters

*   that: [DataRouter](wallaroo-core-topology-DataRouter) val

#### Returns

* [Bool](builtin-Bool) val

---

### migrate_state

```pony
fun box migrate_state(
  target_id: U128 val,
  s: (String val | Array[U8 val] val))
: None val
```
#### Parameters

*   target_id: [U128](builtin-U128) val
*   s: ([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)

#### Returns

* [None](builtin-None) val

---

### ne

```pony
fun box ne(
  that: DataRouter val)
: Bool val
```
#### Parameters

*   that: [DataRouter](wallaroo-core-topology-DataRouter) val

#### Returns

* [Bool](builtin-Bool) val

---

