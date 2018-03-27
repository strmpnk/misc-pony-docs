# _KafkaTopicPartitionState

```pony
class ref _KafkaTopicPartitionState
```

## Constructors

### create

```pony
new ref create(
  partition_error_code': I16 val,
  partition_id': I32 val,
  leader': I32 val,
  replicas': Array[I32 val] val,
  isrs': Array[I32 val] val,
  request_timestamp': I64 val = seq,
  max_bytes': I32 val = seq)
: _KafkaTopicPartitionState ref^
```
#### Parameters

*   partition_error_code': [I16](builtin-I16) val
*   partition_id': [I32](builtin-I32) val
*   leader': [I32](builtin-I32) val
*   replicas': [Array](builtin-Array)\[[I32](builtin-I32) val\] val
*   isrs': [Array](builtin-Array)\[[I32](builtin-I32) val\] val
*   request_timestamp': [I64](builtin-I64) val = seq
*   max_bytes': [I32](builtin-I32) val = seq

#### Returns

* [_KafkaTopicPartitionState](pony-kafka-_KafkaTopicPartitionState) ref^

---

## Public fields

* var partition_error_code: [I16](builtin-I16) val

---

* let partition_id: [I32](builtin-I32) val

---

* var leader: [I32](builtin-I32) val

---

* var replicas: [Array](builtin-Array)\[[I32](builtin-I32) val\] val

---

* var isrs: [Array](builtin-Array)\[[I32](builtin-I32) val\] val

---

* var request_timestamp: [I64](builtin-I64) val

---

* var error_code: [I16](builtin-I16) val

---

* var timestamp: ([I64](builtin-I64) val | [None](builtin-None) val)

---

* var request_offset: [I64](builtin-I64) val

---

* var max_bytes: [I32](builtin-I32) val

---

* var paused: [Bool](builtin-Bool) val

---

* var current_leader: [Bool](builtin-Bool) val

---

* var leader_change_sent_messages: [Array](builtin-Array)\[[ProducerKafkaMessage](pony-kafka-ProducerKafkaMessage) val\] ref

---

* var leader_change_pending_messages: [Array](builtin-Array)\[[ProducerKafkaMessage](pony-kafka-ProducerKafkaMessage) val\] ref

---

* var leader_change: [Bool](builtin-Bool) val

---

* var leader_change_receiver: [Bool](builtin-Bool) val

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

