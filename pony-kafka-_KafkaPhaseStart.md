# _KafkaPhaseStart

```pony
primitive val _KafkaPhaseStart is
  FsmState ref
```

#### Implements

* [FsmState](.-fsm-FsmState) ref

---

## Constructors

### create

```pony
new val create()
: _KafkaPhaseStart val^
```

#### Returns

* [_KafkaPhaseStart](pony-kafka-_KafkaPhaseStart) val^

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
  that: _KafkaPhaseStart val)
: Bool val
```
#### Parameters

*   that: [_KafkaPhaseStart](pony-kafka-_KafkaPhaseStart) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: _KafkaPhaseStart val)
: Bool val
```
#### Parameters

*   that: [_KafkaPhaseStart](pony-kafka-_KafkaPhaseStart) val

#### Returns

* [Bool](builtin-Bool) val

---

