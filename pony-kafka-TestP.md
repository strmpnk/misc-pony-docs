# TestP

```pony
actor tag TestP is
  KafkaProducer ref
```

#### Implements

* [KafkaProducer](pony-kafka-KafkaProducer) ref

---

## Constructors

### create

```pony
new tag create()
: TestP tag^
```

#### Returns

* [TestP](pony-kafka-TestP) tag^

---

## Public Behaviours

### kafka_producer_ready

```pony
be kafka_producer_ready()
```

---

### kafka_message_delivery_report

```pony
be kafka_message_delivery_report(
  delivery_report: KafkaProducerDeliveryReport val)
```
#### Parameters

*   delivery_report: [KafkaProducerDeliveryReport](pony-kafka-KafkaProducerDeliveryReport) val

---

## Public Functions

### create_producer_mapping

```pony
fun ref create_producer_mapping(
  mapping: KafkaProducerMapping ref)
: (KafkaProducerMapping ref | None val)
```
#### Parameters

*   mapping: [KafkaProducerMapping](pony-kafka-KafkaProducerMapping) ref

#### Returns

* ([KafkaProducerMapping](pony-kafka-KafkaProducerMapping) ref | [None](builtin-None) val)

---

### producer_mapping

```pony
fun ref producer_mapping()
: (KafkaProducerMapping ref | None val)
```

#### Returns

* ([KafkaProducerMapping](pony-kafka-KafkaProducerMapping) ref | [None](builtin-None) val)

---

## Private Behaviours

### _create_producer_mapping

```pony
be _create_producer_mapping(
  mapping: KafkaProducerMapping iso)
```
#### Parameters

*   mapping: [KafkaProducerMapping](pony-kafka-KafkaProducerMapping) iso

---

### _update_brokers_and_topic_mapping

```pony
be _update_brokers_and_topic_mapping(
  brokers: HashMap[I32 val, (_KafkaBroker val , KafkaBrokerConnection tag), HashEq[I32 val] val] val,
  topic_mapping: HashMap[String val, HashMap[I32 val, I32 val, HashEq[I32 val] val] ref, HashEq[String val] val] val)
```
#### Parameters

*   brokers: [HashMap](collections-HashMap)\[[I32](builtin-I32) val, ([_KafkaBroker](pony-kafka-_KafkaBroker) val , [KafkaBrokerConnection](pony-kafka-KafkaBrokerConnection) tag), [HashEq](collections-HashEq)\[[I32](builtin-I32) val\] val\] val
*   topic_mapping: [HashMap](collections-HashMap)\[[String](builtin-String) val, [HashMap](collections-HashMap)\[[I32](builtin-I32) val, [I32](builtin-I32) val, [HashEq](collections-HashEq)\[[I32](builtin-I32) val\] val\] ref, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val

---

### _kafka_producer_throttle

```pony
be _kafka_producer_throttle(
  topic_mapping: HashMap[String val, HashMap[I32 val, I32 val, HashEq[I32 val] val] ref, HashEq[String val] val] val,
  ack_requested: Bool val,
  client: KafkaClient tag,
  p: KafkaProducer tag)
```
#### Parameters

*   topic_mapping: [HashMap](collections-HashMap)\[[String](builtin-String) val, [HashMap](collections-HashMap)\[[I32](builtin-I32) val, [I32](builtin-I32) val, [HashEq](collections-HashEq)\[[I32](builtin-I32) val\] val\] ref, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val
*   ack_requested: [Bool](builtin-Bool) val
*   client: [KafkaClient](pony-kafka-KafkaClient) tag
*   p: [KafkaProducer](pony-kafka-KafkaProducer) tag

---

### _kafka_producer_unthrottle

```pony
be _kafka_producer_unthrottle(
  topic_mapping: HashMap[String val, HashMap[I32 val, I32 val, HashEq[I32 val] val] ref, HashEq[String val] val] val,
  ack_requested: Bool val,
  client: KafkaClient tag,
  p: KafkaProducer tag,
  fully_unthrottled: Bool val)
```
#### Parameters

*   topic_mapping: [HashMap](collections-HashMap)\[[String](builtin-String) val, [HashMap](collections-HashMap)\[[I32](builtin-I32) val, [I32](builtin-I32) val, [HashEq](collections-HashEq)\[[I32](builtin-I32) val\] val\] ref, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val
*   ack_requested: [Bool](builtin-Bool) val
*   client: [KafkaClient](pony-kafka-KafkaClient) tag
*   p: [KafkaProducer](pony-kafka-KafkaProducer) tag
*   fully_unthrottled: [Bool](builtin-Bool) val

---

## Private Functions

### _kafka_producer_throttled

```pony
fun ref _kafka_producer_throttled(
  topic_mapping: HashMap[String val, HashMap[I32 val, I32 val, HashEq[I32 val] val] ref, HashEq[String val] val] val)
: None val
```
#### Parameters

*   topic_mapping: [HashMap](collections-HashMap)\[[String](builtin-String) val, [HashMap](collections-HashMap)\[[I32](builtin-I32) val, [I32](builtin-I32) val, [HashEq](collections-HashEq)\[[I32](builtin-I32) val\] val\] ref, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val

#### Returns

* [None](builtin-None) val

---

### _kafka_producer_unthrottled

```pony
fun ref _kafka_producer_unthrottled(
  topic_mapping: HashMap[String val, HashMap[I32 val, I32 val, HashEq[I32 val] val] ref, HashEq[String val] val] val,
  fully_unthrottled: Bool val)
: None val
```
#### Parameters

*   topic_mapping: [HashMap](collections-HashMap)\[[String](builtin-String) val, [HashMap](collections-HashMap)\[[I32](builtin-I32) val, [I32](builtin-I32) val, [HashEq](collections-HashEq)\[[I32](builtin-I32) val\] val\] ref, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val
*   fully_unthrottled: [Bool](builtin-Bool) val

#### Returns

* [None](builtin-None) val

---

