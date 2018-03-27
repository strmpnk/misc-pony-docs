# KafkaClient

```pony
actor tag KafkaClient
```

## Constructors

### create

```pony
new tag create(
  auth: (AmbientAuth val | NetAuth val | TCPAuth val | 
    TCPConnectAuth val),
  conf: KafkaConfig val,
  manager: KafkaClientManager tag,
  broker_connection_factory: KafkaBrokerConnectionFactory val = seq)
: KafkaClient tag^
```
#### Parameters

*   auth: ([AmbientAuth](builtin-AmbientAuth) val | [NetAuth](net-NetAuth) val | [TCPAuth](net-TCPAuth) val | 
    [TCPConnectAuth](net-TCPConnectAuth) val)
*   conf: [KafkaConfig](pony-kafka-KafkaConfig) val
*   manager: [KafkaClientManager](pony-kafka-KafkaClientManager) tag
*   broker_connection_factory: [KafkaBrokerConnectionFactory](pony-kafka-KafkaBrokerConnectionFactory) val = seq

#### Returns

* [KafkaClient](pony-kafka-KafkaClient) tag^

---

## Public fields

* var fully_initialized: [Bool](builtin-Bool) val

---

## Public Behaviours

### update_consumer_message_handler

```pony
be update_consumer_message_handler(
  topic: String val,
  consumer_handler: KafkaConsumerMessageHandler val)
```
#### Parameters

*   topic: [String](builtin-String) val
*   consumer_handler: [KafkaConsumerMessageHandler](pony-kafka-KafkaConsumerMessageHandler) val

---

### register_consumer

```pony
be register_consumer(
  topic: String val,
  c: KafkaConsumer tag)
```
#### Parameters

*   topic: [String](builtin-String) val
*   c: [KafkaConsumer](pony-kafka-KafkaConsumer) tag

---

### register_consumers

```pony
be register_consumers(
  topic: String val,
  consumers: Array[KafkaConsumer tag] val)
```
#### Parameters

*   topic: [String](builtin-String) val
*   consumers: [Array](builtin-Array)\[[KafkaConsumer](pony-kafka-KafkaConsumer) tag\] val

---

### replace_consumers

```pony
be replace_consumers(
  topic: String val,
  consumers: Array[KafkaConsumer tag] val)
```
#### Parameters

*   topic: [String](builtin-String) val
*   consumers: [Array](builtin-Array)\[[KafkaConsumer](pony-kafka-KafkaConsumer) tag\] val

---

### consumer_pause

```pony
be consumer_pause(
  topic: String val,
  partition_id: I32 val)
```
#### Parameters

*   topic: [String](builtin-String) val
*   partition_id: [I32](builtin-I32) val

---

### consumer_pause_all

```pony
be consumer_pause_all()
```

---

### consumer_resume

```pony
be consumer_resume(
  topic: String val,
  partition_id: I32 val)
```
#### Parameters

*   topic: [String](builtin-String) val
*   partition_id: [I32](builtin-I32) val

---

### consumer_resume_all

```pony
be consumer_resume_all()
```

---

### register_producer

```pony
be register_producer(
  p: KafkaProducer tag)
```
#### Parameters

*   p: [KafkaProducer](pony-kafka-KafkaProducer) tag

---

### throttle_ack

```pony
be throttle_ack(
  topic_mapping: HashMap[String val, HashMap[I32 val, I32 val, HashEq[I32 val] val] ref, HashEq[String val] val] val,
  actual_p: KafkaProducer tag,
  sent_p: KafkaProducer tag)
```
#### Parameters

*   topic_mapping: [HashMap](collections-HashMap)\[[String](builtin-String) val, [HashMap](collections-HashMap)\[[I32](builtin-I32) val, [I32](builtin-I32) val, [HashEq](collections-HashEq)\[[I32](builtin-I32) val\] val\] ref, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val
*   actual_p: [KafkaProducer](pony-kafka-KafkaProducer) tag
*   sent_p: [KafkaProducer](pony-kafka-KafkaProducer) tag

---

### unthrottle_ack

```pony
be unthrottle_ack(
  topic_mapping: HashMap[String val, HashMap[I32 val, I32 val, HashEq[I32 val] val] ref, HashEq[String val] val] val,
  actual_p: KafkaProducer tag,
  sent_p: KafkaProducer tag)
```
#### Parameters

*   topic_mapping: [HashMap](collections-HashMap)\[[String](builtin-String) val, [HashMap](collections-HashMap)\[[I32](builtin-I32) val, [I32](builtin-I32) val, [HashEq](collections-HashEq)\[[I32](builtin-I32) val\] val\] ref, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val
*   actual_p: [KafkaProducer](pony-kafka-KafkaProducer) tag
*   sent_p: [KafkaProducer](pony-kafka-KafkaProducer) tag

---

### dispose

```pony
be dispose()
```

---

## Public Functions

### update_consumers_read_only

```pony
fun ref update_consumers_read_only()
: None val
```

#### Returns

* [None](builtin-None) val

---

### update_read_only_topic_mapping

```pony
fun ref update_read_only_topic_mapping()
: None val
```

#### Returns

* [None](builtin-None) val

---

### create_and_send_producer_mappings

```pony
fun box create_and_send_producer_mappings()
: None val
```

#### Returns

* [None](builtin-None) val

---

## Private Behaviours

### _broker_initialized

```pony
be _broker_initialized(
  broker_id: I32 val)
```
#### Parameters

*   broker_id: [I32](builtin-I32) val

---

### _update_metadata

```pony
be _update_metadata(
  meta: _KafkaMetadata val)
```
#### Parameters

*   meta: [_KafkaMetadata](pony-kafka-_KafkaMetadata) val

---

### _throttle_producers

```pony
be _throttle_producers(
  broker_id: I32 val)
```
#### Parameters

*   broker_id: [I32](builtin-I32) val

---

### _unthrottle_producers

```pony
be _unthrottle_producers(
  broker_id: I32 val)
```
#### Parameters

*   broker_id: [I32](builtin-I32) val

---

### _leader_change_throttle

```pony
be _leader_change_throttle(
  topics_to_throttle: HashMap[String val, HashSet[I32 val, HashEq[I32 val] val] iso, HashEq[String val] val] val,
  broker_id: I32 val)
```
#### Parameters

*   topics_to_throttle: [HashMap](collections-HashMap)\[[String](builtin-String) val, [HashSet](collections-HashSet)\[[I32](builtin-I32) val, [HashEq](collections-HashEq)\[[I32](builtin-I32) val\] val\] iso, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val
*   broker_id: [I32](builtin-I32) val

---

### _leader_change_unthrottle

```pony
be _leader_change_unthrottle(
  topics_to_unthrottle: HashMap[String val, HashSet[I32 val, HashEq[I32 val] val] iso, HashEq[String val] val] val,
  broker_id: I32 val)
```
#### Parameters

*   topics_to_unthrottle: [HashMap](collections-HashMap)\[[String](builtin-String) val, [HashSet](collections-HashSet)\[[I32](builtin-I32) val, [HashEq](collections-HashEq)\[[I32](builtin-I32) val\] val\] iso, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val
*   broker_id: [I32](builtin-I32) val

---

### _recoverable_error

```pony
be _recoverable_error(
  error_report: KafkaErrorReport val,
  internal: Bool val = seq)
```
#### Parameters

*   error_report: [KafkaErrorReport](pony-kafka-KafkaErrorReport) val
*   internal: [Bool](builtin-Bool) val = seq

---

### _unrecoverable_error

```pony
be _unrecoverable_error(
  error_report: KafkaErrorReport val)
```
#### Parameters

*   error_report: [KafkaErrorReport](pony-kafka-KafkaErrorReport) val

---

## Private Functions

### _update_consumer_handlers_read_only

```pony
fun ref _update_consumer_handlers_read_only()
: None val
```

#### Returns

* [None](builtin-None) val

---

### _register_consumers

```pony
fun ref _register_consumers(
  topic: String val,
  consumers: Array[KafkaConsumer tag] val)
: None val
```
#### Parameters

*   topic: [String](builtin-String) val
*   consumers: [Array](builtin-Array)\[[KafkaConsumer](pony-kafka-KafkaConsumer) tag\] val

#### Returns

* [None](builtin-None) val

---

