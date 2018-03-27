# _KafkaTopicProducePartitionResponse

```pony
class ref _KafkaTopicProducePartitionResponse
```

## Constructors

### create

```pony
new ref create(
  partition_id': I32 val,
  error_code': I16 val,
  offset': I64 val,
  timestamp': (I64 val | None val) = seq)
: _KafkaTopicProducePartitionResponse ref^
```
#### Parameters

*   partition_id': [I32](builtin-I32) val
*   error_code': [I16](builtin-I16) val
*   offset': [I64](builtin-I64) val
*   timestamp': ([I64](builtin-I64) val | [None](builtin-None) val) = seq

#### Returns

* [_KafkaTopicProducePartitionResponse](pony-kafka-_KafkaTopicProducePartitionResponse) ref^

---

## Public fields

* let partition_id: [I32](builtin-I32) val

---

* let error_code: [I16](builtin-I16) val

---

* let offset: [I64](builtin-I64) val

---

* let timestamp: ([I64](builtin-I64) val | [None](builtin-None) val)

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

