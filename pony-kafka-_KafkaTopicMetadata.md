# _KafkaTopicMetadata

```pony
class ref _KafkaTopicMetadata
```

## Constructors

### create

```pony
new iso create(
  topic_error_code': I16 val,
  topic': String val,
  partitions_metadata': HashMap[I32 val, _KafkaTopicPartitionMetadata val, HashEq[I32 val] val] val,
  is_internal': (Bool val | None val) = seq)
: _KafkaTopicMetadata iso^
```
#### Parameters

*   topic_error_code': [I16](builtin-I16) val
*   topic': [String](builtin-String) val
*   partitions_metadata': [HashMap](collections-HashMap)\[[I32](builtin-I32) val, [_KafkaTopicPartitionMetadata](pony-kafka-_KafkaTopicPartitionMetadata) val, [HashEq](collections-HashEq)\[[I32](builtin-I32) val\] val\] val
*   is_internal': ([Bool](builtin-Bool) val | [None](builtin-None) val) = seq

#### Returns

* [_KafkaTopicMetadata](pony-kafka-_KafkaTopicMetadata) iso^

---

## Public fields

* let topic_error_code: [I16](builtin-I16) val

---

* let topic: [String](builtin-String) val

---

* let is_internal: ([Bool](builtin-Bool) val | [None](builtin-None) val)

---

* let partitions_metadata: [HashMap](collections-HashMap)\[[I32](builtin-I32) val, [_KafkaTopicPartitionMetadata](pony-kafka-_KafkaTopicPartitionMetadata) val, [HashEq](collections-HashEq)\[[I32](builtin-I32) val\] val\] val

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

