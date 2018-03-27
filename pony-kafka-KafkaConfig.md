# KafkaConfig

```pony
class ref KafkaConfig
```

## Constructors

### create

```pony
new ref create(
  logger': Logger[String val] val,
  client_name': String val,
  fetch_interval': U64 val = seq,
  min_fetch_bytes': I32 val = seq,
  max_fetch_bytes': I32 val = seq,
  produce_acks': I16 val = seq,
  produce_timeout_ms': I32 val = seq,
  use_snappy_java_framing': Bool val = seq,
  max_inflight_requests': USize val = seq,
  partition_fetch_max_bytes': I32 val = seq,
  max_message_size': I32 val = seq,
  refresh_metadata_interval': U64 val = seq,
  max_produce_buffer_ms': U64 val = seq,
  max_produce_buffer_messages': U64 val = seq,
  check_crc': Bool val = seq,
  network_sniffer': (KafkaNetworkSniffer tag | None val) = seq)
: KafkaConfig ref^
```
#### Parameters

*   logger': [Logger](.-customlogger-Logger)\[[String](builtin-String) val\] val
*   client_name': [String](builtin-String) val
*   fetch_interval': [U64](builtin-U64) val = seq
*   min_fetch_bytes': [I32](builtin-I32) val = seq
*   max_fetch_bytes': [I32](builtin-I32) val = seq
*   produce_acks': [I16](builtin-I16) val = seq
*   produce_timeout_ms': [I32](builtin-I32) val = seq
*   use_snappy_java_framing': [Bool](builtin-Bool) val = seq
*   max_inflight_requests': [USize](builtin-USize) val = seq
*   partition_fetch_max_bytes': [I32](builtin-I32) val = seq
*   max_message_size': [I32](builtin-I32) val = seq
*   refresh_metadata_interval': [U64](builtin-U64) val = seq
*   max_produce_buffer_ms': [U64](builtin-U64) val = seq
*   max_produce_buffer_messages': [U64](builtin-U64) val = seq
*   check_crc': [Bool](builtin-Bool) val = seq
*   network_sniffer': ([KafkaNetworkSniffer](pony-kafka-KafkaNetworkSniffer) tag | [None](builtin-None) val) = seq

#### Returns

* [KafkaConfig](pony-kafka-KafkaConfig) ref^

---

## Public fields

* let client_name: [String](builtin-String) val

---

* let consumer_topics: [HashSet](collections-HashSet)\[[String](builtin-String) val, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] ref

---

* let producer_topics: [HashSet](collections-HashSet)\[[String](builtin-String) val, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] ref

---

* let topics: [HashMap](collections-HashMap)\[[String](builtin-String) val, [KafkaTopicConfig](pony-kafka-KafkaTopicConfig) ref, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] ref

---

* let brokers: [HashSet](collections-HashSet)\[[_KafkaBroker](pony-kafka-_KafkaBroker) ref, [HashEq](collections-HashEq)\[[_KafkaBroker](pony-kafka-_KafkaBroker) ref\] val\] ref

---

* var replica_id: [I32](builtin-I32) val

---

* let fetch_interval: [U64](builtin-U64) val

---

* let refresh_metadata_interval: [U64](builtin-U64) val

---

* let min_fetch_bytes: [I32](builtin-I32) val

---

* let max_fetch_bytes: [I32](builtin-I32) val

---

* let produce_acks: [I16](builtin-I16) val

---

* let produce_timeout_ms: [I32](builtin-I32) val

---

* let logger: [Logger](.-customlogger-Logger)\[[String](builtin-String) val\] val

---

* let use_snappy_java_framing: [Bool](builtin-Bool) val

---

* let max_inflight_requests: [USize](builtin-USize) val

---

* let partition_fetch_max_bytes: [I32](builtin-I32) val

---

* let max_message_size: [I32](builtin-I32) val

---

* let max_produce_buffer_time: [U64](builtin-U64) val

---

* let max_produce_buffer_messages: [U64](builtin-U64) val

---

* let check_crc: [Bool](builtin-Bool) val

---

* var network_sniffer: ([KafkaNetworkSniffer](pony-kafka-KafkaNetworkSniffer) tag | [None](builtin-None) val)

---

## Public Functions

### add_broker

```pony
fun ref add_broker(
  host: String val,
  port: I32 val = seq)
: None val
```
#### Parameters

*   host: [String](builtin-String) val
*   port: [I32](builtin-I32) val = seq

#### Returns

* [None](builtin-None) val

---

### add_topic_config

```pony
fun ref add_topic_config(
  topic_name: String val,
  role: (KafkaConsumeOnly val | KafkaProduceOnly val | KafkaProduceAndConsume val) = seq,
  producer_message_handler: KafkaProducerMessageHandler val = seq,
  consumer_message_handler: KafkaConsumerMessageHandler val = seq,
  compression: (KafkaNoTopicCompression val | KafkaGzipTopicCompression val | KafkaSnappyTopicCompression val | 
    KafkaLZ4TopicCompression val) = seq,
  default_consumer_start_offset': (KafkaOffsetBeginning val | KafkaOffsetEnd val | I32 val) = seq,
  partitions': (Array[I32 val] val | Array[(I32 val , (KafkaOffsetBeginning val | KafkaOffsetEnd val | I32 val))] val | None val) = seq)
: None val
```
#### Parameters

*   topic_name: [String](builtin-String) val
*   role: ([KafkaConsumeOnly](pony-kafka-KafkaConsumeOnly) val | [KafkaProduceOnly](pony-kafka-KafkaProduceOnly) val | [KafkaProduceAndConsume](pony-kafka-KafkaProduceAndConsume) val) = seq
*   producer_message_handler: [KafkaProducerMessageHandler](pony-kafka-KafkaProducerMessageHandler) val = seq
*   consumer_message_handler: [KafkaConsumerMessageHandler](pony-kafka-KafkaConsumerMessageHandler) val = seq
*   compression: ([KafkaNoTopicCompression](pony-kafka-KafkaNoTopicCompression) val | [KafkaGzipTopicCompression](pony-kafka-KafkaGzipTopicCompression) val | [KafkaSnappyTopicCompression](pony-kafka-KafkaSnappyTopicCompression) val | 
    [KafkaLZ4TopicCompression](pony-kafka-KafkaLZ4TopicCompression) val) = seq
*   default_consumer_start_offset': ([KafkaOffsetBeginning](pony-kafka-KafkaOffsetBeginning) val | [KafkaOffsetEnd](pony-kafka-KafkaOffsetEnd) val | [I32](builtin-I32) val) = seq
*   partitions': ([Array](builtin-Array)\[[I32](builtin-I32) val\] val | [Array](builtin-Array)\[([I32](builtin-I32) val , ([KafkaOffsetBeginning](pony-kafka-KafkaOffsetBeginning) val | [KafkaOffsetEnd](pony-kafka-KafkaOffsetEnd) val | [I32](builtin-I32) val))\] val | [None](builtin-None) val) = seq

#### Returns

* [None](builtin-None) val

---

## Private Functions

### _set_replica_id

```pony
fun ref _set_replica_id(
  replica_id': I32 val)
: None val
```
#### Parameters

*   replica_id': [I32](builtin-I32) val

#### Returns

* [None](builtin-None) val

---

