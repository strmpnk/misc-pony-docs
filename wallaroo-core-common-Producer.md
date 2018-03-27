# Producer

```pony
trait tag Producer is
  Muteable tag,
  Ackable tag,
  AckRequester tag
```

#### Implements

* [Muteable](wallaroo-core-common-Muteable) tag
* [Ackable](wallaroo-core-common-Ackable) tag
* [AckRequester](wallaroo-core-common-AckRequester) tag

---

## Public Behaviours

### mute

```pony
be mute(
  c: Consumer tag)
```
#### Parameters

*   c: [Consumer](wallaroo-core-common-Consumer) tag

---

### unmute

```pony
be unmute(
  c: Consumer tag)
```
#### Parameters

*   c: [Consumer](wallaroo-core-common-Consumer) tag

---

### replay_log_entry

```pony
be replay_log_entry(
  uid: U128 val,
  frac_ids: (Array[U32 val] val | None val),
  statechange_id: U64 val,
  payload: (String val | Array[U8 val] val))
```
#### Parameters

*   uid: [U128](builtin-U128) val
*   frac_ids: ([Array](builtin-Array)\[[U32](builtin-U32) val\] val | [None](builtin-None) val)
*   statechange_id: [U64](builtin-U64) val
*   payload: ([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)

---

### initialize_seq_id_on_recovery

```pony
be initialize_seq_id_on_recovery(
  seq_id: U64 val)
```
#### Parameters

*   seq_id: [U64](builtin-U64) val

---

### log_flushed

```pony
be log_flushed(
  low_watermark: U64 val)
```
#### Parameters

*   low_watermark: [U64](builtin-U64) val

---

### update_watermark

```pony
be update_watermark(
  route_id: U64 val,
  seq_id: U64 val)
```
#### Parameters

*   route_id: [U64](builtin-U64) val
*   seq_id: [U64](builtin-U64) val

---

### request_ack

```pony
be request_ack()
```

---

## Public Functions

### route_to

```pony
fun ref route_to(
  c: Consumer tag)
: (Route ref | None val)
```
#### Parameters

*   c: [Consumer](wallaroo-core-common-Consumer) tag

#### Returns

* ([Route](wallaroo-core-routing-Route) ref | [None](builtin-None) val)

---

### next_sequence_id

```pony
fun ref next_sequence_id()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### current_sequence_id

```pony
fun ref current_sequence_id()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### flush

```pony
fun ref flush(
  low_watermark: U64 val)
: None val
```
#### Parameters

*   low_watermark: [U64](builtin-U64) val

#### Returns

* [None](builtin-None) val

---

### bookkeeping

```pony
fun ref bookkeeping(
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

## Private Functions

### _acker

```pony
fun ref _acker()
: Acker ref
```

#### Returns

* [Acker](wallaroo-ent-watermarking-Acker) ref

---

### _update_watermark

```pony
fun ref _update_watermark(
  route_id: U64 val,
  seq_id: U64 val)
: None val
```
#### Parameters

*   route_id: [U64](builtin-U64) val
*   seq_id: [U64](builtin-U64) val

#### Returns

* [None](builtin-None) val

---

