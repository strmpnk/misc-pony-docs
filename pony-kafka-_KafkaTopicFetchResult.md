# _KafkaTopicFetchResult

```pony
class ref _KafkaTopicFetchResult
```

## Constructors

### create

```pony
new ref create(
  topic': String val,
  partition_responses': HashMap[I32 val, _KafkaTopicPartitionResponse ref, HashEq[I32 val] val] ref)
: _KafkaTopicFetchResult ref^
```
#### Parameters

*   topic': [String](builtin-String) val
*   partition_responses': [HashMap](collections-HashMap)\[[I32](builtin-I32) val, [_KafkaTopicPartitionResponse](pony-kafka-_KafkaTopicPartitionResponse) ref, [HashEq](collections-HashEq)\[[I32](builtin-I32) val\] val\] ref

#### Returns

* [_KafkaTopicFetchResult](pony-kafka-_KafkaTopicFetchResult) ref^

---

## Public fields

* let topic: [String](builtin-String) val

---

* let partition_responses: [HashMap](collections-HashMap)\[[I32](builtin-I32) val, [_KafkaTopicPartitionResponse](pony-kafka-_KafkaTopicPartitionResponse) ref, [HashEq](collections-HashEq)\[[I32](builtin-I32) val\] val\] ref

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

