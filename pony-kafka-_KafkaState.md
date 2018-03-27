# _KafkaState

```pony
class ref _KafkaState
```

## Constructors

### create

```pony
new ref create()
: _KafkaState ref^
```

#### Returns

* [_KafkaState](pony-kafka-_KafkaState) ref^

---

## Public fields

* var controller_id: ([I32](builtin-I32) val | [None](builtin-None) val)

---

* var cluster_id: [String](builtin-String) val

---

* let topics_state: [HashMap](collections-HashMap)\[[String](builtin-String) val, [_KafkaTopicState](pony-kafka-_KafkaTopicState) ref, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] ref

---

* let consumer_unacked_offsets: [HashMap](collections-HashMap)\[[KafkaTopicPartition](pony-kafka-KafkaTopicPartition) val, [HashSet](collections-HashSet)\[[I64](builtin-I64) val, [HashEq](collections-HashEq)\[[I64](builtin-I64) val\] val\] iso, [HashEq](collections-HashEq)\[[KafkaTopicPartition](pony-kafka-KafkaTopicPartition) val\] val\] ref

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

