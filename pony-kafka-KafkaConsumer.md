# KafkaConsumer

```pony
trait ref KafkaConsumer
```

## Public Behaviours

### receive_kafka_message

```pony
be receive_kafka_message(
  value: Array[U8 val] iso,
  key: (Array[U8 val] val | None val),
  msg_metadata: KafkaMessageMetadata val,
  network_received_timestamp: U64 val)
```
#### Parameters

*   value: [Array](builtin-Array)\[[U8](builtin-U8) val\] iso
*   key: ([Array](builtin-Array)\[[U8](builtin-U8) val\] val | [None](builtin-None) val)
*   msg_metadata: [KafkaMessageMetadata](pony-kafka-KafkaMessageMetadata) val
*   network_received_timestamp: [U64](builtin-U64) val

---

