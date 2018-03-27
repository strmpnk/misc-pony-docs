# _KafkaPhaseUpdateOffsets

```pony
primitive val _KafkaPhaseUpdateOffsets is
  FsmState ref
```

#### Implements

* [FsmState](.-fsm-FsmState) ref

---

## Constructors

### create

```pony
new val create()
: _KafkaPhaseUpdateOffsets val^
```

#### Returns

* [_KafkaPhaseUpdateOffsets](pony-kafka-_KafkaPhaseUpdateOffsets) val^

---

## Public Functions

### string

```pony
fun box string()
: String val
```

#### Returns

* [String](builtin-String) val

---

### eq

```pony
fun box eq(
  that: _KafkaPhaseUpdateOffsets val)
: Bool val
```
#### Parameters

*   that: [_KafkaPhaseUpdateOffsets](pony-kafka-_KafkaPhaseUpdateOffsets) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: _KafkaPhaseUpdateOffsets val)
: Bool val
```
#### Parameters

*   that: [_KafkaPhaseUpdateOffsets](pony-kafka-_KafkaPhaseUpdateOffsets) val

#### Returns

* [Bool](builtin-Bool) val

---

