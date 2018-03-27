# TerminusRoute

End of the line route.

We are leaving this process, to either another Wallaroo process
or to an external system.

The only route out of this step is to terminate here. Unlike filtering,
termination can either be immediate (like filtering) or can be delayed
such as "terminate this tuple once we know it has been sent by the sink".


```pony
class ref TerminusRoute
```

## Constructors

### create

```pony
new ref create(
  ack_batch_size': USize val = seq)
: TerminusRoute ref^
```
#### Parameters

*   ack_batch_size': [USize](builtin-USize) val = seq

#### Returns

* [TerminusRoute](wallaroo-ent-watermarking-TerminusRoute) ref^

---

## Public Functions

### terminate

Mark for termination. Termination isn't complete until its acknowledged.


```pony
fun ref terminate(
  i_producer: Producer tag,
  i_route_id: U64 val,
  i_seq_id: U64 val)
: U64 val
```
#### Parameters

*   i_producer: [Producer](wallaroo-core-common-Producer) tag
*   i_route_id: [U64](builtin-U64) val
*   i_seq_id: [U64](builtin-U64) val

#### Returns

* [U64](builtin-U64) val

---

### receive_ack

Acknowledgement that we are done handling a termination.


```pony
fun ref receive_ack(
  seq_id: U64 val)
: None val
```
#### Parameters

*   seq_id: [U64](builtin-U64) val

#### Returns

* [None](builtin-None) val

---

### is_fully_acked

```pony
fun box is_fully_acked()
: Bool val
```

#### Returns

* [Bool](builtin-Bool) val

---

### request_ack

```pony
fun ref request_ack()
: None val
```

#### Returns

* [None](builtin-None) val

---

## Private Functions

### _next_tracking_id

```pony
fun ref _next_tracking_id()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### _maybe_ack

```pony
fun ref _maybe_ack()
: None val
```

#### Returns

* [None](builtin-None) val

---

### _ack

```pony
fun ref _ack()
: None val
```

#### Returns

* [None](builtin-None) val

---

