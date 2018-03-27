# _KafkaTopicState

```pony
class ref _KafkaTopicState
```

## Constructors

### create

```pony
new ref create(
  topic': String val,
  message_handler': KafkaConsumerMessageHandler ref,
  topic_error_code': I16 val = seq,
  is_internal': (Bool val | None val) = seq)
: _KafkaTopicState ref^
```
#### Parameters

*   topic': [String](builtin-String) val
*   message_handler': [KafkaConsumerMessageHandler](pony-kafka-KafkaConsumerMessageHandler) ref
*   topic_error_code': [I16](builtin-I16) val = seq
*   is_internal': ([Bool](builtin-Bool) val | [None](builtin-None) val) = seq

#### Returns

* [_KafkaTopicState](pony-kafka-_KafkaTopicState) ref^

---

## Public fields

* var topic_error_code: [I16](builtin-I16) val

---

* let topic: [String](builtin-String) val

---

* var is_internal: ([Bool](builtin-Bool) val | [None](builtin-None) val)

---

* let partitions_state: [HashMap](collections-HashMap)\[[I32](builtin-I32) val, [_KafkaTopicPartitionState](pony-kafka-_KafkaTopicPartitionState) ref, [HashEq](collections-HashEq)\[[I32](builtin-I32) val\] val\] ref

---

* var consumers: [Array](builtin-Array)\[[KafkaConsumer](pony-kafka-KafkaConsumer) tag\] val

---

* var message_handler: [KafkaConsumerMessageHandler](pony-kafka-KafkaConsumerMessageHandler) ref

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

