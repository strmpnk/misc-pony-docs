# Acker

Handles coordination between different moving parts that are used to
when making decisions of what messages to acknowledge having been handled.


```pony
class ref Acker
```

## Constructors

### create

```pony
new ref create(
  ack_batch_size': USize val = seq)
: Acker ref^
```
#### Parameters

*   ack_batch_size': [USize](builtin-USize) val = seq

#### Returns

* [Acker](wallaroo-ent-watermarking-Acker) ref^

---

## Public Functions

### add_route

```pony
fun ref add_route(
  route: Route ref)
: None val
```
#### Parameters

*   route: [Route](wallaroo-core-routing-Route) ref

#### Returns

* [None](builtin-None) val

---

### remove_route

```pony
fun ref remove_route(
  route: Route ref)
: None val
```
#### Parameters

*   route: [Route](wallaroo-core-routing-Route) ref

#### Returns

* [None](builtin-None) val

---

### sent

```pony
fun ref sent(
  o_route_id: U64 val,
  o_seq_id: U64 val)
: None val
```
#### Parameters

*   o_route_id: [U64](builtin-U64) val
*   o_seq_id: [U64](builtin-U64) val

#### Returns

* [None](builtin-None) val

---

### filtered

Filter out a message or otherwise have this be the end of the line


```pony
fun ref filtered(
  ackable: Ackable ref,
  o_seq_id: U64 val)
: None val
```
#### Parameters

*   ackable: [Ackable](wallaroo-core-common-Ackable) ref
*   o_seq_id: [U64](builtin-U64) val

#### Returns

* [None](builtin-None) val

---

### ack_received

```pony
fun ref ack_received(
  ackable: Ackable ref,
  route_id: U64 val,
  seq_id: U64 val)
: None val
```
#### Parameters

*   ackable: [Ackable](wallaroo-core-common-Ackable) ref
*   route_id: [U64](builtin-U64) val
*   seq_id: [U64](builtin-U64) val

#### Returns

* [None](builtin-None) val

---

### track_incoming_to_outgoing

```pony
fun ref track_incoming_to_outgoing(
  o_seq_id: U64 val,
  i_producer: Producer tag,
  i_route_id: U64 val,
  i_seq_id: U64 val)
: None val
```
#### Parameters

*   o_seq_id: [U64](builtin-U64) val
*   i_producer: [Producer](wallaroo-core-common-Producer) tag
*   i_route_id: [U64](builtin-U64) val
*   i_seq_id: [U64](builtin-U64) val

#### Returns

* [None](builtin-None) val

---

### flushed

```pony
fun ref flushed(
  up_to: U64 val)
: None val
```
#### Parameters

*   up_to: [U64](builtin-U64) val

#### Returns

* [None](builtin-None) val

---

### request_ack

```pony
fun ref request_ack(
  ackable: Ackable ref)
: None val
```
#### Parameters

*   ackable: [Ackable](wallaroo-core-common-Ackable) ref

#### Returns

* [None](builtin-None) val

---

### propose_new_watermark

```pony
fun ref propose_new_watermark()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

## Private Functions

### _add_incoming

```pony
fun ref _add_incoming(
  o_seq_id: U64 val,
  i_producer: Producer tag,
  i_route_id: U64 val,
  i_seq_id: U64 val)
: None val
```
#### Parameters

*   o_seq_id: [U64](builtin-U64) val
*   i_producer: [Producer](wallaroo-core-common-Producer) tag
*   i_route_id: [U64](builtin-U64) val
*   i_seq_id: [U64](builtin-U64) val

#### Returns

* [None](builtin-None) val

---

### _maybe_ack

```pony
fun ref _maybe_ack(
  ackable: Ackable ref)
: None val
```
#### Parameters

*   ackable: [Ackable](wallaroo-core-common-Ackable) ref

#### Returns

* [None](builtin-None) val

---

### _ack

```pony
fun ref _ack(
  ackable: Ackable ref)
: None val
```
#### Parameters

*   ackable: [Ackable](wallaroo-core-common-Ackable) ref

#### Returns

* [None](builtin-None) val

---

