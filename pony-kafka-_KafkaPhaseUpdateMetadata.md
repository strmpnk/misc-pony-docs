# _KafkaPhaseUpdateMetadata

```pony
primitive val _KafkaPhaseUpdateMetadata is
  FsmState ref
```

#### Implements

* [FsmState](.-fsm-FsmState) ref

---

## Constructors

### create

```pony
new val create()
: _KafkaPhaseUpdateMetadata val^
```

#### Returns

* [_KafkaPhaseUpdateMetadata](pony-kafka-_KafkaPhaseUpdateMetadata) val^

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
  that: _KafkaPhaseUpdateMetadata val)
: Bool val
```
#### Parameters

*   that: [_KafkaPhaseUpdateMetadata](pony-kafka-_KafkaPhaseUpdateMetadata) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: _KafkaPhaseUpdateMetadata val)
: Bool val
```
#### Parameters

*   that: [_KafkaPhaseUpdateMetadata](pony-kafka-_KafkaPhaseUpdateMetadata) val

#### Returns

* [Bool](builtin-Bool) val

---

