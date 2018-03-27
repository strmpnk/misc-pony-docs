# KafkaTopicConfig

```pony
class ref KafkaTopicConfig is
  Equatable[KafkaTopicConfig box] ref
```

#### Implements

* [Equatable](builtin-Equatable)\[[KafkaTopicConfig](pony-kafka-KafkaTopicConfig) box\] ref

---

## Constructors

### create

```pony
new ref create(
  topic_name': String val,
  role': (KafkaConsumeOnly val | KafkaProduceOnly val | KafkaProduceAndConsume val) = seq,
  producer_message_handler': KafkaProducerMessageHandler val = seq,
  consumer_message_handler': KafkaConsumerMessageHandler val = seq,
  compression': (KafkaNoTopicCompression val | KafkaGzipTopicCompression val | KafkaSnappyTopicCompression val | 
    KafkaLZ4TopicCompression val) = seq,
  default_consumer_start_offset': (KafkaOffsetBeginning val | KafkaOffsetEnd val | I32 val) = seq,
  partitions': (Array[I32 val] val | Array[(I32 val , (KafkaOffsetBeginning val | KafkaOffsetEnd val | I32 val))] val | None val) = seq)
: KafkaTopicConfig ref^
```
#### Parameters

*   topic_name': [String](builtin-String) val
*   role': ([KafkaConsumeOnly](pony-kafka-KafkaConsumeOnly) val | [KafkaProduceOnly](pony-kafka-KafkaProduceOnly) val | [KafkaProduceAndConsume](pony-kafka-KafkaProduceAndConsume) val) = seq
*   producer_message_handler': [KafkaProducerMessageHandler](pony-kafka-KafkaProducerMessageHandler) val = seq
*   consumer_message_handler': [KafkaConsumerMessageHandler](pony-kafka-KafkaConsumerMessageHandler) val = seq
*   compression': ([KafkaNoTopicCompression](pony-kafka-KafkaNoTopicCompression) val | [KafkaGzipTopicCompression](pony-kafka-KafkaGzipTopicCompression) val | [KafkaSnappyTopicCompression](pony-kafka-KafkaSnappyTopicCompression) val | 
    [KafkaLZ4TopicCompression](pony-kafka-KafkaLZ4TopicCompression) val) = seq
*   default_consumer_start_offset': ([KafkaOffsetBeginning](pony-kafka-KafkaOffsetBeginning) val | [KafkaOffsetEnd](pony-kafka-KafkaOffsetEnd) val | [I32](builtin-I32) val) = seq
*   partitions': ([Array](builtin-Array)\[[I32](builtin-I32) val\] val | [Array](builtin-Array)\[([I32](builtin-I32) val , ([KafkaOffsetBeginning](pony-kafka-KafkaOffsetBeginning) val | [KafkaOffsetEnd](pony-kafka-KafkaOffsetEnd) val | [I32](builtin-I32) val))\] val | [None](builtin-None) val) = seq

#### Returns

* [KafkaTopicConfig](pony-kafka-KafkaTopicConfig) ref^

---

## Public fields

* let topic_name: [String](builtin-String) val

---

* let producer_message_handler: [KafkaProducerMessageHandler](pony-kafka-KafkaProducerMessageHandler) val

---

* let consumer_message_handler: [KafkaConsumerMessageHandler](pony-kafka-KafkaConsumerMessageHandler) val

---

* let role: ([KafkaConsumeOnly](pony-kafka-KafkaConsumeOnly) val | [KafkaProduceOnly](pony-kafka-KafkaProduceOnly) val | [KafkaProduceAndConsume](pony-kafka-KafkaProduceAndConsume) val)

---

* let compression: ([KafkaNoTopicCompression](pony-kafka-KafkaNoTopicCompression) val | [KafkaGzipTopicCompression](pony-kafka-KafkaGzipTopicCompression) val | [KafkaSnappyTopicCompression](pony-kafka-KafkaSnappyTopicCompression) val | 
    [KafkaLZ4TopicCompression](pony-kafka-KafkaLZ4TopicCompression) val)

---

* let partitions: [HashMap](collections-HashMap)\[[I32](builtin-I32) val, ([KafkaOffsetBeginning](pony-kafka-KafkaOffsetBeginning) val | [KafkaOffsetEnd](pony-kafka-KafkaOffsetEnd) val | [I32](builtin-I32) val), [HashEq](collections-HashEq)\[[I32](builtin-I32) val\] val\] ref

---

* let default_consumer_start_offset: ([KafkaOffsetBeginning](pony-kafka-KafkaOffsetBeginning) val | [KafkaOffsetEnd](pony-kafka-KafkaOffsetEnd) val | [I32](builtin-I32) val)

---

## Public Functions

### hash

```pony
fun box hash()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### eq

```pony
fun box eq(
  that: KafkaTopicConfig box)
: Bool val
```
#### Parameters

*   that: [KafkaTopicConfig](pony-kafka-KafkaTopicConfig) box

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: KafkaTopicConfig box)
: Bool val
```
#### Parameters

*   that: [KafkaTopicConfig](pony-kafka-KafkaTopicConfig) box

#### Returns

* [Bool](builtin-Bool) val

---

