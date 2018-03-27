# _KafkaTopicPartitionResponse

```pony
class ref _KafkaTopicPartitionResponse
```

## Constructors

### create

```pony
new ref create(
  partition_id': I32 val,
  error_code': I16 val,
  high_watermark': I64 val,
  largest_offset_seen': I64 val,
  messages': Array[(Array[U8 val] iso , (Array[U8 val] iso | None val | KafkaError val) , KafkaMessageMetadata iso)] iso)
: _KafkaTopicPartitionResponse ref^
```
#### Parameters

*   partition_id': [I32](builtin-I32) val
*   error_code': [I16](builtin-I16) val
*   high_watermark': [I64](builtin-I64) val
*   largest_offset_seen': [I64](builtin-I64) val
*   messages': [Array](builtin-Array)\[([Array](builtin-Array)\[[U8](builtin-U8) val\] iso , ([Array](builtin-Array)\[[U8](builtin-U8) val\] iso | [None](builtin-None) val | [KafkaError](pony-kafka-KafkaError) val) , [KafkaMessageMetadata](pony-kafka-KafkaMessageMetadata) iso)\] iso

#### Returns

* [_KafkaTopicPartitionResponse](pony-kafka-_KafkaTopicPartitionResponse) ref^

---

## Public fields

* let partition_id: [I32](builtin-I32) val

---

* let error_code: [I16](builtin-I16) val

---

* let largest_offset_seen: [I64](builtin-I64) val

---

* let high_watermark: [I64](builtin-I64) val

---

* let messages: [Array](builtin-Array)\[([Array](builtin-Array)\[[U8](builtin-U8) val\] iso , ([Array](builtin-Array)\[[U8](builtin-U8) val\] iso | [None](builtin-None) val | [KafkaError](pony-kafka-KafkaError) val) , [KafkaMessageMetadata](pony-kafka-KafkaMessageMetadata) iso)\] iso

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

