# _KafkaTopicOffset

```pony
class ref _KafkaTopicOffset
```

## Constructors

### create

```pony
new ref create(
  topic': String val,
  partitions_offset': Array[_KafkaTopicPartitionOffset ref] ref)
: _KafkaTopicOffset ref^
```
#### Parameters

*   topic': [String](builtin-String) val
*   partitions_offset': [Array](builtin-Array)\[[_KafkaTopicPartitionOffset](pony-kafka-_KafkaTopicPartitionOffset) ref\] ref

#### Returns

* [_KafkaTopicOffset](pony-kafka-_KafkaTopicOffset) ref^

---

## Public fields

* let topic: [String](builtin-String) val

---

* let partitions_offset: [Array](builtin-Array)\[[_KafkaTopicPartitionOffset](pony-kafka-_KafkaTopicPartitionOffset) ref\] ref

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

