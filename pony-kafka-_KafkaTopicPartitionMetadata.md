# _KafkaTopicPartitionMetadata

```pony
class ref _KafkaTopicPartitionMetadata
```

## Constructors

### create

```pony
new iso create(
  partition_error_code': I16 val,
  partition_id': I32 val,
  leader': I32 val,
  replicas': Array[I32 val] val,
  isrs': Array[I32 val] val,
  request_timestamp': I64 val = seq)
: _KafkaTopicPartitionMetadata iso^
```
#### Parameters

*   partition_error_code': [I16](builtin-I16) val
*   partition_id': [I32](builtin-I32) val
*   leader': [I32](builtin-I32) val
*   replicas': [Array](builtin-Array)\[[I32](builtin-I32) val\] val
*   isrs': [Array](builtin-Array)\[[I32](builtin-I32) val\] val
*   request_timestamp': [I64](builtin-I64) val = seq

#### Returns

* [_KafkaTopicPartitionMetadata](pony-kafka-_KafkaTopicPartitionMetadata) iso^

---

## Public fields

* let partition_error_code: [I16](builtin-I16) val

---

* let partition_id: [I32](builtin-I32) val

---

* let leader: [I32](builtin-I32) val

---

* let replicas: [Array](builtin-Array)\[[I32](builtin-I32) val\] val

---

* let isrs: [Array](builtin-Array)\[[I32](builtin-I32) val\] val

---

* var request_timestamp: [I64](builtin-I64) val

---

* var error_code: [I16](builtin-I16) val

---

* var timestamp: ([I64](builtin-I64) val | [None](builtin-None) val)

---

* var request_offset: [I64](builtin-I64) val

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

