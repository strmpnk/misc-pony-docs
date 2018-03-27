# _OutgoingToIncomingMessageTracker

```pony
class ref _OutgoingToIncomingMessageTracker
```

## Constructors

### create

```pony
new ref create(
  size': USize val = seq)
: _OutgoingToIncomingMessageTracker ref^
```
#### Parameters

*   size': [USize](builtin-USize) val = seq

#### Returns

* [_OutgoingToIncomingMessageTracker](wallaroo-ent-watermarking-_OutgoingToIncomingMessageTracker) ref^

---

## Public Functions

### add

```pony
fun ref add(
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

### evict

```pony
fun ref evict(
  through: U64 val)
: None val
```
#### Parameters

*   through: [U64](builtin-U64) val

#### Returns

* [None](builtin-None) val

---

## Private Functions

### _producer_highs_below

```pony
fun box _producer_highs_below(
  id: U64 val)
: HashMap[(Producer tag , U64 val), U64 val, HashIs[(Producer tag , U64 val)] val] ref
```
#### Parameters

*   id: [U64](builtin-U64) val

#### Returns

* [HashMap](collections-HashMap)\[([Producer](wallaroo-core-common-Producer) tag , [U64](builtin-U64) val), [U64](builtin-U64) val, [HashIs](collections-HashIs)\[([Producer](wallaroo-core-common-Producer) tag , [U64](builtin-U64) val)\] val\] ref

---

### _index_for

Find the highest index that is at or below the supplied SeqId.
Ids in_seq_id_to_incoming ascend monotonically. If this were not
the case, this code would be horribly broken.


```pony
fun box _index_for(
  id: U64 val)
: USize val
```
#### Parameters

*   id: [U64](builtin-U64) val

#### Returns

* [USize](builtin-USize) val

---

### _size

```pony
fun box _size()
: USize val
```

#### Returns

* [USize](builtin-USize) val

---

### _contains

```pony
fun ref _contains(
  seq_id: U64 val)
: Bool val
```
#### Parameters

*   seq_id: [U64](builtin-U64) val

#### Returns

* [Bool](builtin-Bool) val

---

