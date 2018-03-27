# _KafkaTopicProduceResponse

```pony
class ref _KafkaTopicProduceResponse
```

## Constructors

### create

```pony
new ref create(
  topic': String val,
  partition_responses': HashMap[I32 val, _KafkaTopicProducePartitionResponse ref, HashEq[I32 val] val] ref)
: _KafkaTopicProduceResponse ref^
```
#### Parameters

*   topic': [String](builtin-String) val
*   partition_responses': [HashMap](collections-HashMap)\[[I32](builtin-I32) val, [_KafkaTopicProducePartitionResponse](pony-kafka-_KafkaTopicProducePartitionResponse) ref, [HashEq](collections-HashEq)\[[I32](builtin-I32) val\] val\] ref

#### Returns

* [_KafkaTopicProduceResponse](pony-kafka-_KafkaTopicProduceResponse) ref^

---

## Public fields

* let topic: [String](builtin-String) val

---

* let partition_responses: [HashMap](collections-HashMap)\[[I32](builtin-I32) val, [_KafkaTopicProducePartitionResponse](pony-kafka-_KafkaTopicProducePartitionResponse) ref, [HashEq](collections-HashEq)\[[I32](builtin-I32) val\] val\] ref

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

