# KafkaBrokerConnection

```pony
trait ref KafkaBrokerConnection is
  CustomTCPConnection ref
```

#### Implements

* [CustomTCPConnection](.-customnet-CustomTCPConnection) ref

---

## Public Behaviours

### send_kafka_messages

```pony
be send_kafka_messages(
  topic: String val,
  msgs_to_send: HashMap[I32 val, Array[ProducerKafkaMessage val] iso, HashEq[I32 val] val] val,
  auth: _KafkaProducerAuth val)
```
#### Parameters

*   topic: [String](builtin-String) val
*   msgs_to_send: [HashMap](collections-HashMap)\[[I32](builtin-I32) val, [Array](builtin-Array)\[[ProducerKafkaMessage](pony-kafka-ProducerKafkaMessage) val\] iso, [HashEq](collections-HashEq)\[[I32](builtin-I32) val\] val\] val
*   auth: [_KafkaProducerAuth](pony-kafka-_KafkaProducerAuth) val

---

### send_kafka_message

```pony
be send_kafka_message(
  topic: String val,
  partition_id: I32 val,
  msg_to_send: ProducerKafkaMessage val,
  auth: _KafkaProducerAuth val)
```
#### Parameters

*   topic: [String](builtin-String) val
*   partition_id: [I32](builtin-I32) val
*   msg_to_send: [ProducerKafkaMessage](pony-kafka-ProducerKafkaMessage) val
*   auth: [_KafkaProducerAuth](pony-kafka-_KafkaProducerAuth) val

---

### write

Write a single sequence of bytes.


```pony
be write(
  data: (String val | Array[U8 val] val))
```
#### Parameters

*   data: ([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)

---

### queue

Queue a single sequence of bytes on linux.
Do nothing on windows.


```pony
be queue(
  data: (String val | Array[U8 val] val))
```
#### Parameters

*   data: ([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)

---

### writev

Write a sequence of sequences of bytes.


```pony
be writev(
  data: ByteSeqIter val)
```
#### Parameters

*   data: [ByteSeqIter](builtin-ByteSeqIter) val

---

### queuev

Queue a sequence of sequences of bytes on linux.
Do nothing on windows.


```pony
be queuev(
  data: ByteSeqIter val)
```
#### Parameters

*   data: [ByteSeqIter](builtin-ByteSeqIter) val

---

### send_queue

Write pending queue to network on linux.
Do nothing on windows.


```pony
be send_queue()
```

---

### set_notify

Change the notifier.


```pony
be set_notify(
  notify: CustomTCPConnectionNotify iso)
```
#### Parameters

*   notify: [CustomTCPConnectionNotify](.-customnet-CustomTCPConnectionNotify) iso

---

### mute

```pony
be mute(
  d: Any tag)
```
#### Parameters

*   d: [Any](builtin-Any) tag

---

### unmute

```pony
be unmute(
  d: Any tag)
```
#### Parameters

*   d: [Any](builtin-Any) tag

---

### dispose

```pony
be dispose()
```

---

### reconnect

```pony
be reconnect()
```

---

## Public Functions

### get_handler

```pony
fun ref get_handler()
: TCPConnectionHandler ref
```

#### Returns

* [TCPConnectionHandler](.-customnet-TCPConnectionHandler) ref

---

### expect

```pony
fun ref expect(
  qty: USize val = seq)
: None val
```
#### Parameters

*   qty: [USize](builtin-USize) val = seq

#### Returns

* [None](builtin-None) val

---

## Private Behaviours

### _update_brokers_list

```pony
be _update_brokers_list(
  brokers_list: HashMap[I32 val, (_KafkaBroker val , KafkaBrokerConnection tag), HashEq[I32 val] val] val)
```
#### Parameters

*   brokers_list: [HashMap](collections-HashMap)\[[I32](builtin-I32) val, ([_KafkaBroker](pony-kafka-_KafkaBroker) val , [KafkaBrokerConnection](pony-kafka-KafkaBrokerConnection) tag), [HashEq](collections-HashEq)\[[I32](builtin-I32) val\] val\] val

---

### _update_consumer_message_handler

```pony
be _update_consumer_message_handler(
  topic: String val,
  consumer_handler: KafkaConsumerMessageHandler val)
```
#### Parameters

*   topic: [String](builtin-String) val
*   consumer_handler: [KafkaConsumerMessageHandler](pony-kafka-KafkaConsumerMessageHandler) val

---

### _update_consumers

```pony
be _update_consumers(
  topic_consumers: HashMap[String val, Array[KafkaConsumer tag] val, HashEq[String val] val] val)
```
#### Parameters

*   topic_consumers: [HashMap](collections-HashMap)\[[String](builtin-String) val, [Array](builtin-Array)\[[KafkaConsumer](pony-kafka-KafkaConsumer) tag\] val, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val

---

### _consumer_pause

```pony
be _consumer_pause(
  topic: String val,
  partition_id: I32 val)
```
#### Parameters

*   topic: [String](builtin-String) val
*   partition_id: [I32](builtin-I32) val

---

### _consumer_pause_all

```pony
be _consumer_pause_all()
```

---

### _consumer_resume

```pony
be _consumer_resume(
  topic: String val,
  partition_id: I32 val)
```
#### Parameters

*   topic: [String](builtin-String) val
*   partition_id: [I32](builtin-I32) val

---

### _consumer_resume_all

```pony
be _consumer_resume_all()
```

---

### _consume_messages

```pony
be _consume_messages()
```

---

### _refresh_metadata

```pony
be _refresh_metadata()
```

---

### _send_pending_messages

```pony
be _send_pending_messages()
```

---

### _leader_change_throttle_ack

```pony
be _leader_change_throttle_ack(
  topics_to_throttle: HashMap[String val, HashSet[I32 val, HashEq[I32 val] val] iso, HashEq[String val] val] val)
```
#### Parameters

*   topics_to_throttle: [HashMap](collections-HashMap)\[[String](builtin-String) val, [HashSet](collections-HashSet)\[[I32](builtin-I32) val, [HashEq](collections-HashEq)\[[I32](builtin-I32) val\] val\] iso, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val

---

### _update_metadata

```pony
be _update_metadata(
  meta: _KafkaMetadata val)
```
#### Parameters

*   meta: [_KafkaMetadata](pony-kafka-_KafkaMetadata) val

---

### _leader_change_msgs

```pony
be _leader_change_msgs(
  meta: _KafkaMetadata val,
  topic: String val,
  partition_id: I32 val,
  msgs: HashMap[I32 val, Array[ProducerKafkaMessage val] iso, HashEq[I32 val] val] val,
  request_offset: I64 val)
```
#### Parameters

*   meta: [_KafkaMetadata](pony-kafka-_KafkaMetadata) val
*   topic: [String](builtin-String) val
*   partition_id: [I32](builtin-I32) val
*   msgs: [HashMap](collections-HashMap)\[[I32](builtin-I32) val, [Array](builtin-Array)\[[ProducerKafkaMessage](pony-kafka-ProducerKafkaMessage) val\] iso, [HashEq](collections-HashEq)\[[I32](builtin-I32) val\] val\] val
*   request_offset: [I64](builtin-I64) val

---

### _event_notify

```pony
be _event_notify(
  event: Pointer[AsioEvent val] tag,
  flags: U32 val,
  arg: U32 val)
```
#### Parameters

*   event: [Pointer](builtin-Pointer)\[[AsioEvent](builtin-AsioEvent) val\] tag
*   flags: [U32](builtin-U32) val
*   arg: [U32](builtin-U32) val

---

### _read_again

```pony
be _read_again()
```

---

