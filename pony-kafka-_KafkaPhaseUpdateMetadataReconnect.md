# _KafkaPhaseUpdateMetadataReconnect

```pony
primitive val _KafkaPhaseUpdateMetadataReconnect is
  FsmState ref
```

#### Implements

* [FsmState](.-fsm-FsmState) ref

---

## Constructors

### create

```pony
new val create()
: _KafkaPhaseUpdateMetadataReconnect val^
```

#### Returns

* [_KafkaPhaseUpdateMetadataReconnect](pony-kafka-_KafkaPhaseUpdateMetadataReconnect) val^

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
  that: _KafkaPhaseUpdateMetadataReconnect val)
: Bool val
```
#### Parameters

*   that: [_KafkaPhaseUpdateMetadataReconnect](pony-kafka-_KafkaPhaseUpdateMetadataReconnect) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: _KafkaPhaseUpdateMetadataReconnect val)
: Bool val
```
#### Parameters

*   that: [_KafkaPhaseUpdateMetadataReconnect](pony-kafka-_KafkaPhaseUpdateMetadataReconnect) val

#### Returns

* [Bool](builtin-Bool) val

---

