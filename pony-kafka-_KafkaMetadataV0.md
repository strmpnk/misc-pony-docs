# _KafkaMetadataV0

```pony
primitive val _KafkaMetadataV0 is
  _KafkaMetadataApi val
```

#### Implements

* [_KafkaMetadataApi](pony-kafka-_KafkaMetadataApi) val

---

## Constructors

### create

```pony
new val create()
: _KafkaMetadataV0 val^
```

#### Returns

* [_KafkaMetadataV0](pony-kafka-_KafkaMetadataV0) val^

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

### encode_request

```pony
fun box encode_request(
  correlation_id: I32 val,
  conf: KafkaConfig val)
: Array[(String val | Array[U8 val] val)] iso^
```
#### Parameters

*   correlation_id: [I32](builtin-I32) val
*   conf: [KafkaConfig](pony-kafka-KafkaConfig) val

#### Returns

* [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] iso^

---

### encode_request_body

```pony
fun box encode_request_body(
  wb: Writer ref,
  conf: KafkaConfig val)
: None val
```
#### Parameters

*   wb: [Writer](.-custombuffered-Writer) ref
*   conf: [KafkaConfig](pony-kafka-KafkaConfig) val

#### Returns

* [None](builtin-None) val

---

### decode_response

```pony
fun box decode_response(
  logger: Logger[String val] val,
  rb: IsoReader ref)
: _KafkaMetadata val ?
```
#### Parameters

*   logger: [Logger](.-customlogger-Logger)\[[String](builtin-String) val\] val
*   rb: [IsoReader](.-custombuffered-IsoReader) ref

#### Returns

* [_KafkaMetadata](pony-kafka-_KafkaMetadata) val ?

---

### decode_topics_metadata

```pony
fun box decode_topics_metadata(
  logger: Logger[String val] val,
  rb: IsoReader ref)
: HashMap[String val, _KafkaTopicMetadata val, HashEq[String val] val] val ?
```
#### Parameters

*   logger: [Logger](.-customlogger-Logger)\[[String](builtin-String) val\] val
*   rb: [IsoReader](.-custombuffered-IsoReader) ref

#### Returns

* [HashMap](collections-HashMap)\[[String](builtin-String) val, [_KafkaTopicMetadata](pony-kafka-_KafkaTopicMetadata) val, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val ?

---

### decode_topic_metadata

```pony
fun box decode_topic_metadata(
  logger: Logger[String val] val,
  rb: IsoReader ref)
: (String val , _KafkaTopicMetadata val) ?
```
#### Parameters

*   logger: [Logger](.-customlogger-Logger)\[[String](builtin-String) val\] val
*   rb: [IsoReader](.-custombuffered-IsoReader) ref

#### Returns

* ([String](builtin-String) val , [_KafkaTopicMetadata](pony-kafka-_KafkaTopicMetadata) val) ?

---

### decode_partitions_metadata

```pony
fun box decode_partitions_metadata(
  logger: Logger[String val] val,
  rb: IsoReader ref)
: HashMap[I32 val, _KafkaTopicPartitionMetadata val, HashEq[I32 val] val] val ?
```
#### Parameters

*   logger: [Logger](.-customlogger-Logger)\[[String](builtin-String) val\] val
*   rb: [IsoReader](.-custombuffered-IsoReader) ref

#### Returns

* [HashMap](collections-HashMap)\[[I32](builtin-I32) val, [_KafkaTopicPartitionMetadata](pony-kafka-_KafkaTopicPartitionMetadata) val, [HashEq](collections-HashEq)\[[I32](builtin-I32) val\] val\] val ?

---

### decode_partition_metadata

```pony
fun box decode_partition_metadata(
  logger: Logger[String val] val,
  rb: IsoReader ref)
: (I32 val , _KafkaTopicPartitionMetadata val) ?
```
#### Parameters

*   logger: [Logger](.-customlogger-Logger)\[[String](builtin-String) val\] val
*   rb: [IsoReader](.-custombuffered-IsoReader) ref

#### Returns

* ([I32](builtin-I32) val , [_KafkaTopicPartitionMetadata](pony-kafka-_KafkaTopicPartitionMetadata) val) ?

---

### decode_brokers

```pony
fun box decode_brokers(
  logger: Logger[String val] val,
  rb: IsoReader ref)
: Array[_KafkaBroker val] val ?
```
#### Parameters

*   logger: [Logger](.-customlogger-Logger)\[[String](builtin-String) val\] val
*   rb: [IsoReader](.-custombuffered-IsoReader) ref

#### Returns

* [Array](builtin-Array)\[[_KafkaBroker](pony-kafka-_KafkaBroker) val\] val ?

---

### decode_broker

```pony
fun box decode_broker(
  logger: Logger[String val] val,
  rb: IsoReader ref)
: _KafkaBroker val ?
```
#### Parameters

*   logger: [Logger](.-customlogger-Logger)\[[String](builtin-String) val\] val
*   rb: [IsoReader](.-custombuffered-IsoReader) ref

#### Returns

* [_KafkaBroker](pony-kafka-_KafkaBroker) val ?

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
  that: _KafkaMetadataV0 val)
: Bool val
```
#### Parameters

*   that: [_KafkaMetadataV0](pony-kafka-_KafkaMetadataV0) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: _KafkaMetadataV0 val)
: Bool val
```
#### Parameters

*   that: [_KafkaMetadataV0](pony-kafka-_KafkaMetadataV0) val

#### Returns

* [Bool](builtin-Bool) val

---

