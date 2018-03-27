# KafkaConsumerMessageHandler

```pony
trait ref KafkaConsumerMessageHandler
```

## Public Functions

### apply

```pony
fun ref apply(
  consumers: Array[KafkaConsumer tag] val,
  key: (Array[U8 val] box | None val),
  msg_metadata: KafkaMessageMetadata val)
: (KafkaConsumer tag | None val)
```
#### Parameters

*   consumers: [Array](builtin-Array)\[[KafkaConsumer](pony-kafka-KafkaConsumer) tag\] val
*   key: ([Array](builtin-Array)\[[U8](builtin-U8) val\] box | [None](builtin-None) val)
*   msg_metadata: [KafkaMessageMetadata](pony-kafka-KafkaMessageMetadata) val

#### Returns

* ([KafkaConsumer](pony-kafka-KafkaConsumer) tag | [None](builtin-None) val)

---

### clone

```pony
fun box clone()
: KafkaConsumerMessageHandler iso^
```

#### Returns

* [KafkaConsumerMessageHandler](pony-kafka-KafkaConsumerMessageHandler) iso^

---

