# KafkaConfigOptions

```pony
class val KafkaConfigOptions
```

## Constructors

### create

```pony
new iso create(
  client_name': String val,
  client_mode': (KafkaConsumeOnly val | KafkaProduceOnly val | KafkaProduceAndConsume val),
  topic': String val,
  brokers': Array[(String val , I32 val)] val,
  log_level': String val = seq,
  max_produce_buffer_ms': U64 val = seq,
  max_message_size': I32 val = seq,
  producer_compression': String val = seq,
  produce_acks': I16 val = seq,
  check_crc': Bool val = seq,
  produce_timeout_ms': I32 val = seq,
  max_inflight_requests': USize val = seq,
  fetch_interval': U64 val = seq,
  min_fetch_bytes': I32 val = seq,
  max_fetch_bytes': I32 val = seq,
  partition_fetch_max_bytes': I32 val = seq,
  offset_default': String val = seq,
  partitions': String val = seq)
: KafkaConfigOptions iso^
```
#### Parameters

*   client_name': [String](builtin-String) val
*   client_mode': ([KafkaConsumeOnly](pony-kafka-KafkaConsumeOnly) val | [KafkaProduceOnly](pony-kafka-KafkaProduceOnly) val | [KafkaProduceAndConsume](pony-kafka-KafkaProduceAndConsume) val)
*   topic': [String](builtin-String) val
*   brokers': [Array](builtin-Array)\[([String](builtin-String) val , [I32](builtin-I32) val)\] val
*   log_level': [String](builtin-String) val = seq
*   max_produce_buffer_ms': [U64](builtin-U64) val = seq
*   max_message_size': [I32](builtin-I32) val = seq
*   producer_compression': [String](builtin-String) val = seq
*   produce_acks': [I16](builtin-I16) val = seq
*   check_crc': [Bool](builtin-Bool) val = seq
*   produce_timeout_ms': [I32](builtin-I32) val = seq
*   max_inflight_requests': [USize](builtin-USize) val = seq
*   fetch_interval': [U64](builtin-U64) val = seq
*   min_fetch_bytes': [I32](builtin-I32) val = seq
*   max_fetch_bytes': [I32](builtin-I32) val = seq
*   partition_fetch_max_bytes': [I32](builtin-I32) val = seq
*   offset_default': [String](builtin-String) val = seq
*   partitions': [String](builtin-String) val = seq

#### Returns

* [KafkaConfigOptions](pony-kafka-KafkaConfigOptions) iso^

---

## Public fields

* var client_name: [String](builtin-String) val

---

* var client_mode: ([KafkaConsumeOnly](pony-kafka-KafkaConsumeOnly) val | [KafkaProduceOnly](pony-kafka-KafkaProduceOnly) val | [KafkaProduceAndConsume](pony-kafka-KafkaProduceAndConsume) val)

---

* var topic: [String](builtin-String) val

---

* var brokers: [Array](builtin-Array)\[([String](builtin-String) val , [I32](builtin-I32) val)\] val

---

* var log_level: [String](builtin-String) val

---

* var max_produce_buffer_ms: [U64](builtin-U64) val

---

* var max_message_size: [I32](builtin-I32) val

---

* var producer_compression: [String](builtin-String) val

---

* var produce_acks: [I16](builtin-I16) val

---

* var check_crc: [Bool](builtin-Bool) val

---

* var produce_timeout_ms: [I32](builtin-I32) val

---

* var max_inflight_requests: [USize](builtin-USize) val

---

* var fetch_interval: [U64](builtin-U64) val

---

* var min_fetch_bytes: [I32](builtin-I32) val

---

* var max_fetch_bytes: [I32](builtin-I32) val

---

* var partition_fetch_max_bytes: [I32](builtin-I32) val

---

* var offset_default: [String](builtin-String) val

---

* var partitions: [String](builtin-String) val

---

