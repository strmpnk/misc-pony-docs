# _KafkaProduceV0

```pony
primitive val _KafkaProduceV0 is
  _KafkaProduceApi val
```

#### Implements

* [_KafkaProduceApi](pony-kafka-_KafkaProduceApi) val

---

## Constructors

### create

```pony
new val create()
: _KafkaProduceV0 val^
```

#### Returns

* [_KafkaProduceV0](pony-kafka-_KafkaProduceV0) val^

---

## Public Functions

### version

```pony
fun box version()
: I16 val
```

#### Returns

* [I16](builtin-I16) val

---

### min_broker_version

```pony
fun box min_broker_version()
: String val
```

#### Returns

* [String](builtin-String) val

---

### combine_and_split_by_message_size_single

```pony
fun box combine_and_split_by_message_size_single(
  conf: KafkaConfig val,
  pending_buffer: Array[(I32 val , U64 val , HashMap[String val, HashMap[I32 val, Array[ProducerKafkaMessage val] ref, HashEq[I32 val] val] ref, HashEq[String val] val] ref)] ref,
  topic: String val,
  partition_id: I32 val,
  msg: ProducerKafkaMessage val,
  topics_state: HashMap[String val, _KafkaTopicState ref, HashEq[String val] val] ref)
: None val ?
```
#### Parameters

*   conf: [KafkaConfig](pony-kafka-KafkaConfig) val
*   pending_buffer: [Array](builtin-Array)\[([I32](builtin-I32) val , [U64](builtin-U64) val , [HashMap](collections-HashMap)\[[String](builtin-String) val, [HashMap](collections-HashMap)\[[I32](builtin-I32) val, [Array](builtin-Array)\[[ProducerKafkaMessage](pony-kafka-ProducerKafkaMessage) val\] ref, [HashEq](collections-HashEq)\[[I32](builtin-I32) val\] val\] ref, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] ref)\] ref
*   topic: [String](builtin-String) val
*   partition_id: [I32](builtin-I32) val
*   msg: [ProducerKafkaMessage](pony-kafka-ProducerKafkaMessage) val
*   topics_state: [HashMap](collections-HashMap)\[[String](builtin-String) val, [_KafkaTopicState](pony-kafka-_KafkaTopicState) ref, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] ref

#### Returns

* [None](builtin-None) val ?

---

### combine_and_split_by_message_size

```pony
fun box combine_and_split_by_message_size(
  conf: KafkaConfig val,
  pending_buffer: Array[(I32 val , U64 val , HashMap[String val, HashMap[I32 val, Array[ProducerKafkaMessage val] ref, HashEq[I32 val] val] ref, HashEq[String val] val] ref)] ref,
  topic: String val,
  msgs: HashMap[I32 val, Array[ProducerKafkaMessage val] iso, HashEq[I32 val] val] val,
  topics_state: HashMap[String val, _KafkaTopicState ref, HashEq[String val] val] ref)
: None val ?
```
#### Parameters

*   conf: [KafkaConfig](pony-kafka-KafkaConfig) val
*   pending_buffer: [Array](builtin-Array)\[([I32](builtin-I32) val , [U64](builtin-U64) val , [HashMap](collections-HashMap)\[[String](builtin-String) val, [HashMap](collections-HashMap)\[[I32](builtin-I32) val, [Array](builtin-Array)\[[ProducerKafkaMessage](pony-kafka-ProducerKafkaMessage) val\] ref, [HashEq](collections-HashEq)\[[I32](builtin-I32) val\] val\] ref, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] ref)\] ref
*   topic: [String](builtin-String) val
*   msgs: [HashMap](collections-HashMap)\[[I32](builtin-I32) val, [Array](builtin-Array)\[[ProducerKafkaMessage](pony-kafka-ProducerKafkaMessage) val\] iso, [HashEq](collections-HashEq)\[[I32](builtin-I32) val\] val\] val
*   topics_state: [HashMap](collections-HashMap)\[[String](builtin-String) val, [_KafkaTopicState](pony-kafka-_KafkaTopicState) ref, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] ref

#### Returns

* [None](builtin-None) val ?

---

### encode_request

```pony
fun box encode_request(
  correlation_id: I32 val,
  conf: KafkaConfig val,
  msgs: HashMap[String val, HashMap[I32 val, Array[ProducerKafkaMessage val] ref, HashEq[I32 val] val] ref, HashEq[String val] val] ref)
: Array[(String val | Array[U8 val] val)] iso^
```
#### Parameters

*   correlation_id: [I32](builtin-I32) val
*   conf: [KafkaConfig](pony-kafka-KafkaConfig) val
*   msgs: [HashMap](collections-HashMap)\[[String](builtin-String) val, [HashMap](collections-HashMap)\[[I32](builtin-I32) val, [Array](builtin-Array)\[[ProducerKafkaMessage](pony-kafka-ProducerKafkaMessage) val\] ref, [HashEq](collections-HashEq)\[[I32](builtin-I32) val\] val\] ref, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] ref

#### Returns

* [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] iso^

---

### encode_request_body

```pony
fun box encode_request_body(
  wb: Writer ref,
  conf: KafkaConfig val,
  msgs: HashMap[String val, HashMap[I32 val, Array[ProducerKafkaMessage val] ref, HashEq[I32 val] val] ref, HashEq[String val] val] ref,
  message_set_version: I8 val)
: None val
```
#### Parameters

*   wb: [Writer](.-custombuffered-Writer) ref
*   conf: [KafkaConfig](pony-kafka-KafkaConfig) val
*   msgs: [HashMap](collections-HashMap)\[[String](builtin-String) val, [HashMap](collections-HashMap)\[[I32](builtin-I32) val, [Array](builtin-Array)\[[ProducerKafkaMessage](pony-kafka-ProducerKafkaMessage) val\] ref, [HashEq](collections-HashEq)\[[I32](builtin-I32) val\] val\] ref, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] ref
*   message_set_version: [I8](builtin-I8) val

#### Returns

* [None](builtin-None) val

---

### decode_request

```pony
fun box decode_request(
  broker_conn: KafkaBrokerConnection tag,
  logger: Logger[String val] val,
  rb: IsoReader ref)
: (I16 val , I32 val , HashMap[String val, HashMap[I32 val, Array[(Array[U8 val] iso , (Array[U8 val] iso | None val | KafkaError val) , KafkaMessageMetadata iso)] val, HashEq[I32 val] val] val, HashEq[String val] val] val) ?
```
#### Parameters

*   broker_conn: [KafkaBrokerConnection](pony-kafka-KafkaBrokerConnection) tag
*   logger: [Logger](.-customlogger-Logger)\[[String](builtin-String) val\] val
*   rb: [IsoReader](.-custombuffered-IsoReader) ref

#### Returns

* ([I16](builtin-I16) val , [I32](builtin-I32) val , [HashMap](collections-HashMap)\[[String](builtin-String) val, [HashMap](collections-HashMap)\[[I32](builtin-I32) val, [Array](builtin-Array)\[([Array](builtin-Array)\[[U8](builtin-U8) val\] iso , ([Array](builtin-Array)\[[U8](builtin-U8) val\] iso | [None](builtin-None) val | [KafkaError](pony-kafka-KafkaError) val) , [KafkaMessageMetadata](pony-kafka-KafkaMessageMetadata) iso)\] val, [HashEq](collections-HashEq)\[[I32](builtin-I32) val\] val\] val, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val) ?

---

### decode_response

```pony
fun box decode_response(
  logger: Logger[String val] val,
  rb: IsoReader ref)
: (HashMap[String val, _KafkaTopicProduceResponse ref, HashEq[String val] val] ref , I32 val) ?
```
#### Parameters

*   logger: [Logger](.-customlogger-Logger)\[[String](builtin-String) val\] val
*   rb: [IsoReader](.-custombuffered-IsoReader) ref

#### Returns

* ([HashMap](collections-HashMap)\[[String](builtin-String) val, [_KafkaTopicProduceResponse](pony-kafka-_KafkaTopicProduceResponse) ref, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] ref , [I32](builtin-I32) val) ?

---

### decode_topic_produce_response

```pony
fun box decode_topic_produce_response(
  logger: Logger[String val] val,
  rb: IsoReader ref)
: (String val , _KafkaTopicProduceResponse ref) ?
```
#### Parameters

*   logger: [Logger](.-customlogger-Logger)\[[String](builtin-String) val\] val
*   rb: [IsoReader](.-custombuffered-IsoReader) ref

#### Returns

* ([String](builtin-String) val , [_KafkaTopicProduceResponse](pony-kafka-_KafkaTopicProduceResponse) ref) ?

---

### decode_topic_produce_partition_response

```pony
fun box decode_topic_produce_partition_response(
  logger: Logger[String val] val,
  rb: IsoReader ref)
: (I32 val , _KafkaTopicProducePartitionResponse ref) ?
```
#### Parameters

*   logger: [Logger](.-customlogger-Logger)\[[String](builtin-String) val\] val
*   rb: [IsoReader](.-custombuffered-IsoReader) ref

#### Returns

* ([I32](builtin-I32) val , [_KafkaTopicProducePartitionResponse](pony-kafka-_KafkaTopicProducePartitionResponse) ref) ?

---

### api_key

```pony
fun box api_key()
: I16 val
```

#### Returns

* [I16](builtin-I16) val

---

### string

```pony
fun box string()
: String val
```

#### Returns

* [String](builtin-String) val

---

### apply

```pony
fun box apply()
: (I16 val , I16 val)
```

#### Returns

* ([I16](builtin-I16) val , [I16](builtin-I16) val)

---

### eq

```pony
fun box eq(
  that: _KafkaProduceV0 val)
: Bool val
```
#### Parameters

*   that: [_KafkaProduceV0](pony-kafka-_KafkaProduceV0) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: _KafkaProduceV0 val)
: Bool val
```
#### Parameters

*   that: [_KafkaProduceV0](pony-kafka-_KafkaProduceV0) val

#### Returns

* [Bool](builtin-Bool) val

---

## Private Functions

### _combine_and_split_by_message_size_single

```pony
fun box _combine_and_split_by_message_size_single(
  conf: KafkaConfig val,
  pending_buffer: Array[(I32 val , U64 val , HashMap[String val, HashMap[I32 val, Array[ProducerKafkaMessage val] ref, HashEq[I32 val] val] ref, HashEq[String val] val] ref)] ref,
  topic: String val,
  partition_id: I32 val,
  msg: ProducerKafkaMessage val,
  topics_state: HashMap[String val, _KafkaTopicState ref, HashEq[String val] val] ref,
  message_set_version: I8 val)
: None val ?
```
#### Parameters

*   conf: [KafkaConfig](pony-kafka-KafkaConfig) val
*   pending_buffer: [Array](builtin-Array)\[([I32](builtin-I32) val , [U64](builtin-U64) val , [HashMap](collections-HashMap)\[[String](builtin-String) val, [HashMap](collections-HashMap)\[[I32](builtin-I32) val, [Array](builtin-Array)\[[ProducerKafkaMessage](pony-kafka-ProducerKafkaMessage) val\] ref, [HashEq](collections-HashEq)\[[I32](builtin-I32) val\] val\] ref, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] ref)\] ref
*   topic: [String](builtin-String) val
*   partition_id: [I32](builtin-I32) val
*   msg: [ProducerKafkaMessage](pony-kafka-ProducerKafkaMessage) val
*   topics_state: [HashMap](collections-HashMap)\[[String](builtin-String) val, [_KafkaTopicState](pony-kafka-_KafkaTopicState) ref, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] ref
*   message_set_version: [I8](builtin-I8) val

#### Returns

* [None](builtin-None) val ?

---

### _combine_and_split_by_message_size

```pony
fun box _combine_and_split_by_message_size(
  conf: KafkaConfig val,
  pending_buffer: Array[(I32 val , U64 val , HashMap[String val, HashMap[I32 val, Array[ProducerKafkaMessage val] ref, HashEq[I32 val] val] ref, HashEq[String val] val] ref)] ref,
  topic: String val,
  topic_msgs: HashMap[I32 val, Array[ProducerKafkaMessage val] iso, HashEq[I32 val] val] val,
  topics_state: HashMap[String val, _KafkaTopicState ref, HashEq[String val] val] ref,
  message_set_version: I8 val)
: None val ?
```
#### Parameters

*   conf: [KafkaConfig](pony-kafka-KafkaConfig) val
*   pending_buffer: [Array](builtin-Array)\[([I32](builtin-I32) val , [U64](builtin-U64) val , [HashMap](collections-HashMap)\[[String](builtin-String) val, [HashMap](collections-HashMap)\[[I32](builtin-I32) val, [Array](builtin-Array)\[[ProducerKafkaMessage](pony-kafka-ProducerKafkaMessage) val\] ref, [HashEq](collections-HashEq)\[[I32](builtin-I32) val\] val\] ref, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] ref)\] ref
*   topic: [String](builtin-String) val
*   topic_msgs: [HashMap](collections-HashMap)\[[I32](builtin-I32) val, [Array](builtin-Array)\[[ProducerKafkaMessage](pony-kafka-ProducerKafkaMessage) val\] iso, [HashEq](collections-HashEq)\[[I32](builtin-I32) val\] val\] val
*   topics_state: [HashMap](collections-HashMap)\[[String](builtin-String) val, [_KafkaTopicState](pony-kafka-_KafkaTopicState) ref, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] ref
*   message_set_version: [I8](builtin-I8) val

#### Returns

* [None](builtin-None) val ?

---

