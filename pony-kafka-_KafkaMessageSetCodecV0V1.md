# _KafkaMessageSetCodecV0V1

```pony
primitive val _KafkaMessageSetCodecV0V1
```

## Constructors

### create

```pony
new val create()
: _KafkaMessageSetCodecV0V1 val^
```

#### Returns

* [_KafkaMessageSetCodecV0V1](pony-kafka-_KafkaMessageSetCodecV0V1) val^

---

## Public Functions

### encode

```pony
fun box encode(
  conf: KafkaConfig val,
  wb: Writer ref,
  msgs: Array[ProducerKafkaMessage val] box,
  version: I8 val,
  compression: (KafkaNoTopicCompression val | KafkaGzipTopicCompression val | KafkaSnappyTopicCompression val | 
    KafkaLZ4TopicCompression val),
  compressed_message_set: Bool val = seq)
: None val
```
#### Parameters

*   conf: [KafkaConfig](pony-kafka-KafkaConfig) val
*   wb: [Writer](.-custombuffered-Writer) ref
*   msgs: [Array](builtin-Array)\[[ProducerKafkaMessage](pony-kafka-ProducerKafkaMessage) val\] box
*   version: [I8](builtin-I8) val
*   compression: ([KafkaNoTopicCompression](pony-kafka-KafkaNoTopicCompression) val | [KafkaGzipTopicCompression](pony-kafka-KafkaGzipTopicCompression) val | [KafkaSnappyTopicCompression](pony-kafka-KafkaSnappyTopicCompression) val | 
    [KafkaLZ4TopicCompression](pony-kafka-KafkaLZ4TopicCompression) val)
*   compressed_message_set: [Bool](builtin-Bool) val = seq

#### Returns

* [None](builtin-None) val

---

### encode_message

```pony
fun box encode_message(
  wb: Writer ref,
  msg: ProducerKafkaMessage val,
  offset: I64 val,
  version: I8 val,
  compression: (KafkaNoTopicCompression val | KafkaGzipTopicCompression val | KafkaSnappyTopicCompression val | 
    KafkaLZ4TopicCompression val) = seq)
: None val
```
#### Parameters

*   wb: [Writer](.-custombuffered-Writer) ref
*   msg: [ProducerKafkaMessage](pony-kafka-ProducerKafkaMessage) val
*   offset: [I64](builtin-I64) val
*   version: [I8](builtin-I8) val
*   compression: ([KafkaNoTopicCompression](pony-kafka-KafkaNoTopicCompression) val | [KafkaGzipTopicCompression](pony-kafka-KafkaGzipTopicCompression) val | [KafkaSnappyTopicCompression](pony-kafka-KafkaSnappyTopicCompression) val | 
    [KafkaLZ4TopicCompression](pony-kafka-KafkaLZ4TopicCompression) val) = seq

#### Returns

* [None](builtin-None) val

---

### encoded_size

```pony
fun box encoded_size(
  conf: KafkaConfig val,
  size: I32 val,
  msgs: Array[ProducerKafkaMessage val] val,
  version: I8 val)
: (I32 val , Array[ProducerKafkaMessage val] val , Array[ProducerKafkaMessage val] val)
```
#### Parameters

*   conf: [KafkaConfig](pony-kafka-KafkaConfig) val
*   size: [I32](builtin-I32) val
*   msgs: [Array](builtin-Array)\[[ProducerKafkaMessage](pony-kafka-ProducerKafkaMessage) val\] val
*   version: [I8](builtin-I8) val

#### Returns

* ([I32](builtin-I32) val , [Array](builtin-Array)\[[ProducerKafkaMessage](pony-kafka-ProducerKafkaMessage) val\] val , [Array](builtin-Array)\[[ProducerKafkaMessage](pony-kafka-ProducerKafkaMessage) val\] val)

---

### encoded_message_size

```pony
fun box encoded_message_size(
  msg: ProducerKafkaMessage val,
  version: I8 val)
: I32 val
```
#### Parameters

*   msg: [ProducerKafkaMessage](pony-kafka-ProducerKafkaMessage) val
*   version: [I8](builtin-I8) val

#### Returns

* [I32](builtin-I32) val

---

### decode

```pony
fun box decode(
  broker_conn: KafkaBrokerConnection tag,
  logger: Logger[String val] val,
  topic_partition: KafkaTopicPartition val,
  msg_data: Array[U8 val] iso,
  part_state: (_KafkaTopicPartitionState ref | None val),
  log_append_timestamp: (I64 val | None val) = seq,
  check_crc: Bool val = seq,
  err_str: String val = seq)
: (I64 val , Array[(Array[U8 val] iso , (Array[U8 val] iso | None val | KafkaError val) , KafkaMessageMetadata iso)] iso^)
```
#### Parameters

*   broker_conn: [KafkaBrokerConnection](pony-kafka-KafkaBrokerConnection) tag
*   logger: [Logger](.-customlogger-Logger)\[[String](builtin-String) val\] val
*   topic_partition: [KafkaTopicPartition](pony-kafka-KafkaTopicPartition) val
*   msg_data: [Array](builtin-Array)\[[U8](builtin-U8) val\] iso
*   part_state: ([_KafkaTopicPartitionState](pony-kafka-_KafkaTopicPartitionState) ref | [None](builtin-None) val)
*   log_append_timestamp: ([I64](builtin-I64) val | [None](builtin-None) val) = seq
*   check_crc: [Bool](builtin-Bool) val = seq
*   err_str: [String](builtin-String) val = seq

#### Returns

* ([I64](builtin-I64) val , [Array](builtin-Array)\[([Array](builtin-Array)\[[U8](builtin-U8) val\] iso , ([Array](builtin-Array)\[[U8](builtin-U8) val\] iso | [None](builtin-None) val | [KafkaError](pony-kafka-KafkaError) val) , [KafkaMessageMetadata](pony-kafka-KafkaMessageMetadata) iso)\] iso^)

---

### decode_message

```pony
fun box decode_message(
  broker_conn: KafkaBrokerConnection tag,
  logger: Logger[String val] val,
  topic_partition: KafkaTopicPartition val,
  offset: I64 val,
  crc: I32 val,
  msg_data: Array[U8 val] iso,
  part_state: (_KafkaTopicPartitionState ref | None val),
  log_append_timestamp: (I64 val | None val),
  check_crc: Bool val,
  err_str: String val = seq)
: (I64 val , Array[(Array[U8 val] iso , (Array[U8 val] iso | None val | KafkaError val) , KafkaMessageMetadata iso)] iso^)
```
#### Parameters

*   broker_conn: [KafkaBrokerConnection](pony-kafka-KafkaBrokerConnection) tag
*   logger: [Logger](.-customlogger-Logger)\[[String](builtin-String) val\] val
*   topic_partition: [KafkaTopicPartition](pony-kafka-KafkaTopicPartition) val
*   offset: [I64](builtin-I64) val
*   crc: [I32](builtin-I32) val
*   msg_data: [Array](builtin-Array)\[[U8](builtin-U8) val\] iso
*   part_state: ([_KafkaTopicPartitionState](pony-kafka-_KafkaTopicPartitionState) ref | [None](builtin-None) val)
*   log_append_timestamp: ([I64](builtin-I64) val | [None](builtin-None) val)
*   check_crc: [Bool](builtin-Bool) val
*   err_str: [String](builtin-String) val = seq

#### Returns

* ([I64](builtin-I64) val , [Array](builtin-Array)\[([Array](builtin-Array)\[[U8](builtin-U8) val\] iso , ([Array](builtin-Array)\[[U8](builtin-U8) val\] iso | [None](builtin-None) val | [KafkaError](pony-kafka-KafkaError) val) , [KafkaMessageMetadata](pony-kafka-KafkaMessageMetadata) iso)\] iso^)

---

### eq

```pony
fun box eq(
  that: _KafkaMessageSetCodecV0V1 val)
: Bool val
```
#### Parameters

*   that: [_KafkaMessageSetCodecV0V1](pony-kafka-_KafkaMessageSetCodecV0V1) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: _KafkaMessageSetCodecV0V1 val)
: Bool val
```
#### Parameters

*   that: [_KafkaMessageSetCodecV0V1](pony-kafka-_KafkaMessageSetCodecV0V1) val

#### Returns

* [Bool](builtin-Bool) val

---

