# MapPartitionConsumerMessageHandler

```pony
class ref MapPartitionConsumerMessageHandler is
  KafkaConsumerMessageHandler ref
```

#### Implements

* [KafkaConsumerMessageHandler](pony-kafka-KafkaConsumerMessageHandler) ref

---

## Constructors

### create

```pony
new ref create(
  consumers: HashMap[I32 val, KafkaConsumer tag, HashEq[I32 val] val] val)
: MapPartitionConsumerMessageHandler ref^
```
#### Parameters

*   consumers: [HashMap](collections-HashMap)\[[I32](builtin-I32) val, [KafkaConsumer](pony-kafka-KafkaConsumer) tag, [HashEq](collections-HashEq)\[[I32](builtin-I32) val\] val\] val

#### Returns

* [MapPartitionConsumerMessageHandler](wallaroo-core-source-kafka_source-MapPartitionConsumerMessageHandler) ref^

---

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

