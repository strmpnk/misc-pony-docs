# KafkaMessageMetadata

```pony
class ref KafkaMessageMetadata
```

## Constructors

### _create

```pony
new ref _create(
  created_by: KafkaBrokerConnection tag,
  offset: I64 val,
  crc: I32 val,
  computed_crc: I32 val,
  crc_check_failed: Bool val,
  magic_byte: I8 val,
  attributes: I8 val,
  timestamp: (I64 val | None val),
  timestamp_type: (KafkaTimestampNotAvailable val | KafkaCreateTimestamp val | KafkaLogAppendTimestamp val),
  topic_partition: KafkaTopicPartition val)
: KafkaMessageMetadata ref^
```
#### Parameters

*   created_by: [KafkaBrokerConnection](pony-kafka-KafkaBrokerConnection) tag
*   offset: [I64](builtin-I64) val
*   crc: [I32](builtin-I32) val
*   computed_crc: [I32](builtin-I32) val
*   crc_check_failed: [Bool](builtin-Bool) val
*   magic_byte: [I8](builtin-I8) val
*   attributes: [I8](builtin-I8) val
*   timestamp: ([I64](builtin-I64) val | [None](builtin-None) val)
*   timestamp_type: ([KafkaTimestampNotAvailable](pony-kafka-KafkaTimestampNotAvailable) val | [KafkaCreateTimestamp](pony-kafka-KafkaCreateTimestamp) val | [KafkaLogAppendTimestamp](pony-kafka-KafkaLogAppendTimestamp) val)
*   topic_partition: [KafkaTopicPartition](pony-kafka-KafkaTopicPartition) val

#### Returns

* [KafkaMessageMetadata](pony-kafka-KafkaMessageMetadata) ref^

---

## Public Functions

### get_offset

```pony
fun box get_offset()
: I64 val
```

#### Returns

* [I64](builtin-I64) val

---

### get_topic

```pony
fun box get_topic()
: String val
```

#### Returns

* [String](builtin-String) val

---

### get_partition_id

```pony
fun box get_partition_id()
: I32 val
```

#### Returns

* [I32](builtin-I32) val

---

### get_timestamp

```pony
fun box get_timestamp()
: ((I64 val | None val) , (KafkaTimestampNotAvailable val | KafkaCreateTimestamp val | KafkaLogAppendTimestamp val))
```

#### Returns

* (([I64](builtin-I64) val | [None](builtin-None) val) , ([KafkaTimestampNotAvailable](pony-kafka-KafkaTimestampNotAvailable) val | [KafkaCreateTimestamp](pony-kafka-KafkaCreateTimestamp) val | [KafkaLogAppendTimestamp](pony-kafka-KafkaLogAppendTimestamp) val))

---

### string

```pony
fun box string()
: String val
```

#### Returns

* [String](builtin-String) val

---

## Private Functions

### _get_topic_partition

```pony
fun box _get_topic_partition()
: KafkaTopicPartition val
```

#### Returns

* [KafkaTopicPartition](pony-kafka-KafkaTopicPartition) val

---

### _update_offset

```pony
fun ref _update_offset(
  offset: I64 val)
: None val
```
#### Parameters

*   offset: [I64](builtin-I64) val

#### Returns

* [None](builtin-None) val

---

### _get_created_by

```pony
fun val _get_created_by()
: KafkaBrokerConnection tag
```

#### Returns

* [KafkaBrokerConnection](pony-kafka-KafkaBrokerConnection) tag

---

