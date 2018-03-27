# _KafkaHandler

```pony
class ref _KafkaHandler is
  CustomTCPConnectionNotify ref
```

#### Implements

* [CustomTCPConnectionNotify](.-customnet-CustomTCPConnectionNotify) ref

---

## Constructors

### create

```pony
new ref create(
  client: KafkaClient tag,
  conf: KafkaConfig val,
  topic_consumer_handlers: HashMap[String val, KafkaConsumerMessageHandler val, HashEq[String val] val] val,
  connection_broker_id: I32 val = seq,
  reconnect_closed_delay: U64 val = seq,
  reconnect_failed_delay: U64 val = seq,
  num_reconnects: U8 val = seq)
: _KafkaHandler ref^
```
#### Parameters

*   client: [KafkaClient](pony-kafka-KafkaClient) tag
*   conf: [KafkaConfig](pony-kafka-KafkaConfig) val
*   topic_consumer_handlers: [HashMap](collections-HashMap)\[[String](builtin-String) val, [KafkaConsumerMessageHandler](pony-kafka-KafkaConsumerMessageHandler) val, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val
*   connection_broker_id: [I32](builtin-I32) val = seq
*   reconnect_closed_delay: [U64](builtin-U64) val = seq
*   reconnect_failed_delay: [U64](builtin-U64) val = seq
*   num_reconnects: [U8](builtin-U8) val = seq

#### Returns

* [_KafkaHandler](pony-kafka-_KafkaHandler) ref^

---

## Public fields

* var send_batch_timer: ([Timer](time-Timer) tag | [None](builtin-None) val)

---

* var metadata_refresh_timer: ([Timer](time-Timer) tag | [None](builtin-None) val)

---

* var metadata_refresh_request_outstanding: [Bool](builtin-Bool) val

---

* var fetch_data_timer: ([Timer](time-Timer) tag | [None](builtin-None) val)

---

## Public Functions

### done_and_consume

```pony
fun ref done_and_consume(
  conn: KafkaBrokerConnection ref)
: None val
```
#### Parameters

*   conn: [KafkaBrokerConnection](pony-kafka-KafkaBrokerConnection) ref

#### Returns

* [None](builtin-None) val

---

### done_and_consume_reconnect

```pony
fun ref done_and_consume_reconnect(
  conn: KafkaBrokerConnection ref)
: None val
```
#### Parameters

*   conn: [KafkaBrokerConnection](pony-kafka-KafkaBrokerConnection) ref

#### Returns

* [None](builtin-None) val

---

### received

```pony
fun ref received(
  conn: CustomTCPConnection ref,
  data: Array[U8 val] iso,
  times: USize val)
: Bool val
```
#### Parameters

*   conn: [CustomTCPConnection](.-customnet-CustomTCPConnection) ref
*   data: [Array](builtin-Array)\[[U8](builtin-U8) val\] iso
*   times: [USize](builtin-USize) val

#### Returns

* [Bool](builtin-Bool) val

---

### accepted

```pony
fun ref accepted(
  conn: CustomTCPConnection ref)
: None val
```
#### Parameters

*   conn: [CustomTCPConnection](.-customnet-CustomTCPConnection) ref

#### Returns

* [None](builtin-None) val

---

### before_reconnecting

```pony
fun ref before_reconnecting(
  conn: CustomTCPConnection ref)
: None val
```
#### Parameters

*   conn: [CustomTCPConnection](.-customnet-CustomTCPConnection) ref

#### Returns

* [None](builtin-None) val

---

### connecting

```pony
fun ref connecting(
  conn: CustomTCPConnection ref,
  count: U32 val)
: None val
```
#### Parameters

*   conn: [CustomTCPConnection](.-customnet-CustomTCPConnection) ref
*   count: [U32](builtin-U32) val

#### Returns

* [None](builtin-None) val

---

### connected

```pony
fun ref connected(
  conn: CustomTCPConnection ref)
: None val
```
#### Parameters

*   conn: [CustomTCPConnection](.-customnet-CustomTCPConnection) ref

#### Returns

* [None](builtin-None) val

---

### expect

```pony
fun ref expect(
  conn: CustomTCPConnection ref,
  qty: USize val)
: USize val
```
#### Parameters

*   conn: [CustomTCPConnection](.-customnet-CustomTCPConnection) ref
*   qty: [USize](builtin-USize) val

#### Returns

* [USize](builtin-USize) val

---

### connect_failed

```pony
fun ref connect_failed(
  conn: CustomTCPConnection ref)
: None val
```
#### Parameters

*   conn: [CustomTCPConnection](.-customnet-CustomTCPConnection) ref

#### Returns

* [None](builtin-None) val

---

### auth_failed

```pony
fun ref auth_failed(
  conn: CustomTCPConnection ref)
: None val
```
#### Parameters

*   conn: [CustomTCPConnection](.-customnet-CustomTCPConnection) ref

#### Returns

* [None](builtin-None) val

---

### closed

```pony
fun ref closed(
  conn: CustomTCPConnection ref)
: None val
```
#### Parameters

*   conn: [CustomTCPConnection](.-customnet-CustomTCPConnection) ref

#### Returns

* [None](builtin-None) val

---

### throttled

```pony
fun ref throttled(
  conn: CustomTCPConnection ref)
: None val
```
#### Parameters

*   conn: [CustomTCPConnection](.-customnet-CustomTCPConnection) ref

#### Returns

* [None](builtin-None) val

---

### unthrottled

```pony
fun ref unthrottled(
  conn: CustomTCPConnection ref)
: None val
```
#### Parameters

*   conn: [CustomTCPConnection](.-customnet-CustomTCPConnection) ref

#### Returns

* [None](builtin-None) val

---

### dispose

```pony
fun box dispose()
: None val
```

#### Returns

* [None](builtin-None) val

---

### payload_length

```pony
fun ref payload_length(
  data: Array[U8 val] iso)
: USize val ?
```
#### Parameters

*   data: [Array](builtin-Array)\[[U8](builtin-U8) val\] iso

#### Returns

* [USize](builtin-USize) val ?

---

### initialize_connection

```pony
fun ref initialize_connection(
  conn: KafkaBrokerConnection ref)
: None val ?
```
#### Parameters

*   conn: [KafkaBrokerConnection](pony-kafka-KafkaBrokerConnection) ref

#### Returns

* [None](builtin-None) val ?

---

### set_fallback_api_versions

```pony
fun ref set_fallback_api_versions(
  conn: KafkaBrokerConnection ref)
: None val
```
#### Parameters

*   conn: [KafkaBrokerConnection](pony-kafka-KafkaBrokerConnection) ref

#### Returns

* [None](builtin-None) val

---

### send_kafka_message

```pony
fun ref send_kafka_message(
  conn: KafkaBrokerConnection ref,
  topic: String val,
  partition_id: I32 val,
  msg: ProducerKafkaMessage val,
  auth: _KafkaProducerAuth val)
: None val
```
#### Parameters

*   conn: [KafkaBrokerConnection](pony-kafka-KafkaBrokerConnection) ref
*   topic: [String](builtin-String) val
*   partition_id: [I32](builtin-I32) val
*   msg: [ProducerKafkaMessage](pony-kafka-ProducerKafkaMessage) val
*   auth: [_KafkaProducerAuth](pony-kafka-_KafkaProducerAuth) val

#### Returns

* [None](builtin-None) val

---

### send_kafka_messages

```pony
fun ref send_kafka_messages(
  conn: KafkaBrokerConnection ref,
  topic: String val,
  msgs: HashMap[I32 val, Array[ProducerKafkaMessage val] iso, HashEq[I32 val] val] val,
  auth: _KafkaProducerAuth val)
: None val
```
#### Parameters

*   conn: [KafkaBrokerConnection](pony-kafka-KafkaBrokerConnection) ref
*   topic: [String](builtin-String) val
*   msgs: [HashMap](collections-HashMap)\[[I32](builtin-I32) val, [Array](builtin-Array)\[[ProducerKafkaMessage](pony-kafka-ProducerKafkaMessage) val\] iso, [HashEq](collections-HashEq)\[[I32](builtin-I32) val\] val\] val
*   auth: [_KafkaProducerAuth](pony-kafka-_KafkaProducerAuth) val

#### Returns

* [None](builtin-None) val

---

### process_pending_buffer

```pony
fun ref process_pending_buffer(
  conn: KafkaBrokerConnection ref,
  send_all_but_one: Bool val = seq)
: None val
```
#### Parameters

*   conn: [KafkaBrokerConnection](pony-kafka-KafkaBrokerConnection) ref
*   send_all_but_one: [Bool](builtin-Bool) val = seq

#### Returns

* [None](builtin-None) val

---

### produce_messages

```pony
fun ref produce_messages(
  size: I32 val,
  num_msgs: U64 val,
  msgs: HashMap[String val, HashMap[I32 val, Array[ProducerKafkaMessage val] ref, HashEq[I32 val] val] ref, HashEq[String val] val] ref)
: (Array[(String val | Array[U8 val] val)] val | None val)
```
#### Parameters

*   size: [I32](builtin-I32) val
*   num_msgs: [U64](builtin-U64) val
*   msgs: [HashMap](collections-HashMap)\[[String](builtin-String) val, [HashMap](collections-HashMap)\[[I32](builtin-I32) val, [Array](builtin-Array)\[[ProducerKafkaMessage](pony-kafka-ProducerKafkaMessage) val\] ref, [HashEq](collections-HashEq)\[[I32](builtin-I32) val\] val\] ref, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] ref

#### Returns

* ([Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val | [None](builtin-None) val)

---

### consume_messages

```pony
fun ref consume_messages(
  conn: KafkaBrokerConnection ref)
: None val
```
#### Parameters

*   conn: [KafkaBrokerConnection](pony-kafka-KafkaBrokerConnection) ref

#### Returns

* [None](builtin-None) val

---

### fetch_messages

```pony
fun ref fetch_messages()
: (Array[(String val | Array[U8 val] val)] iso^ | None val)
```

#### Returns

* ([Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] iso^ | [None](builtin-None) val)

---

### update_brokers_list

```pony
fun ref update_brokers_list(
  brokers_list: HashMap[I32 val, (_KafkaBroker val , KafkaBrokerConnection tag), HashEq[I32 val] val] val)
: None val
```
#### Parameters

*   brokers_list: [HashMap](collections-HashMap)\[[I32](builtin-I32) val, ([_KafkaBroker](pony-kafka-_KafkaBroker) val , [KafkaBrokerConnection](pony-kafka-KafkaBrokerConnection) tag), [HashEq](collections-HashEq)\[[I32](builtin-I32) val\] val\] val

#### Returns

* [None](builtin-None) val

---

### update_broker_api_versions

```pony
fun ref update_broker_api_versions()
: Array[(String val | Array[U8 val] val)] iso^
```

#### Returns

* [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] iso^

---

### refresh_metadata

```pony
fun ref refresh_metadata(
  conn: KafkaBrokerConnection ref)
: None val
```
#### Parameters

*   conn: [KafkaBrokerConnection](pony-kafka-KafkaBrokerConnection) ref

#### Returns

* [None](builtin-None) val

---

### request_metadata

```pony
fun ref request_metadata()
: (Array[(String val | Array[U8 val] val)] iso^ | None val)
```

#### Returns

* ([Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] iso^ | [None](builtin-None) val)

---

### refresh_offsets

```pony
fun ref refresh_offsets(
  conn: KafkaBrokerConnection ref)
: None val
```
#### Parameters

*   conn: [KafkaBrokerConnection](pony-kafka-KafkaBrokerConnection) ref

#### Returns

* [None](builtin-None) val

---

### request_offsets

```pony
fun ref request_offsets()
: (Array[(String val | Array[U8 val] val)] iso^ | None val)
```

#### Returns

* ([Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] iso^ | [None](builtin-None) val)

---

### update_offsets

```pony
fun ref update_offsets(
  offsets: Array[_KafkaTopicOffset ref] ref)
: None val
```
#### Parameters

*   offsets: [Array](builtin-Array)\[[_KafkaTopicOffset](pony-kafka-_KafkaTopicOffset) ref\] ref

#### Returns

* [None](builtin-None) val

---

### process_produce_response

```pony
fun ref process_produce_response(
  produce_response: HashMap[String val, _KafkaTopicProduceResponse ref, HashEq[String val] val] ref,
  throttle_time: I32 val,
  msgs: HashMap[String val, HashMap[I32 val, Array[ProducerKafkaMessage val] ref, HashEq[I32 val] val] ref, HashEq[String val] val] ref,
  conn: KafkaBrokerConnection ref)
: None val
```
#### Parameters

*   produce_response: [HashMap](collections-HashMap)\[[String](builtin-String) val, [_KafkaTopicProduceResponse](pony-kafka-_KafkaTopicProduceResponse) ref, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] ref
*   throttle_time: [I32](builtin-I32) val
*   msgs: [HashMap](collections-HashMap)\[[String](builtin-String) val, [HashMap](collections-HashMap)\[[I32](builtin-I32) val, [Array](builtin-Array)\[[ProducerKafkaMessage](pony-kafka-ProducerKafkaMessage) val\] ref, [HashEq](collections-HashEq)\[[I32](builtin-I32) val\] val\] ref, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] ref
*   conn: [KafkaBrokerConnection](pony-kafka-KafkaBrokerConnection) ref

#### Returns

* [None](builtin-None) val

---

### handle_partition_leader_change

```pony
fun ref handle_partition_leader_change(
  conn: KafkaBrokerConnection ref,
  kafka_error: KafkaError val,
  topic: String val,
  partition_id: I32 val,
  msgs: Array[ProducerKafkaMessage val] ref,
  partition_state: _KafkaTopicPartitionState ref)
: None val
```
#### Parameters

*   conn: [KafkaBrokerConnection](pony-kafka-KafkaBrokerConnection) ref
*   kafka_error: [KafkaError](pony-kafka-KafkaError) val
*   topic: [String](builtin-String) val
*   partition_id: [I32](builtin-I32) val
*   msgs: [Array](builtin-Array)\[[ProducerKafkaMessage](pony-kafka-ProducerKafkaMessage) val\] ref
*   partition_state: [_KafkaTopicPartitionState](pony-kafka-_KafkaTopicPartitionState) ref

#### Returns

* [None](builtin-None) val

---

### handle_partition_leader_change_pending_buffer

```pony
fun ref handle_partition_leader_change_pending_buffer(
  topic: String val,
  partition_id: I32 val,
  partition_state: _KafkaTopicPartitionState ref)
: None val
```
#### Parameters

*   topic: [String](builtin-String) val
*   partition_id: [I32](builtin-I32) val
*   partition_state: [_KafkaTopicPartitionState](pony-kafka-_KafkaTopicPartitionState) ref

#### Returns

* [None](builtin-None) val

---

### process_fetched_data

```pony
fun ref process_fetched_data(
  conn: KafkaBrokerConnection ref,
  fetch_results: HashMap[String val, _KafkaTopicFetchResult ref, HashEq[String val] val] ref,
  network_received_timestamp: U64 val)
: None val
```
#### Parameters

*   conn: [KafkaBrokerConnection](pony-kafka-KafkaBrokerConnection) ref
*   fetch_results: [HashMap](collections-HashMap)\[[String](builtin-String) val, [_KafkaTopicFetchResult](pony-kafka-_KafkaTopicFetchResult) ref, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] ref
*   network_received_timestamp: [U64](builtin-U64) val

#### Returns

* [None](builtin-None) val

---

### update_offsets_fetch_response

```pony
fun ref update_offsets_fetch_response(
  fetch_results: HashMap[String val, _KafkaTopicFetchResult ref, HashEq[String val] val] ref)
: Bool val
```
#### Parameters

*   fetch_results: [HashMap](collections-HashMap)\[[String](builtin-String) val, [_KafkaTopicFetchResult](pony-kafka-_KafkaTopicFetchResult) ref, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] ref

#### Returns

* [Bool](builtin-Bool) val

---

### decode_response

```pony
fun ref decode_response(
  conn: KafkaBrokerConnection ref,
  data: Array[U8 val] iso,
  network_received_timestamp: U64 val)
: None val
```
#### Parameters

*   conn: [KafkaBrokerConnection](pony-kafka-KafkaBrokerConnection) ref
*   data: [Array](builtin-Array)\[[U8](builtin-U8) val\] iso
*   network_received_timestamp: [U64](builtin-U64) val

#### Returns

* [None](builtin-None) val

---

### update_api_versions_to_use

```pony
fun ref update_api_versions_to_use(
  api_versions_supported: Array[(I16 val , I16 val , I16 val)] ref)
: None val
```
#### Parameters

*   api_versions_supported: [Array](builtin-Array)\[([I16](builtin-I16) val , [I16](builtin-I16) val , [I16](builtin-I16) val)\] ref

#### Returns

* [None](builtin-None) val

---

### sent

```pony
fun ref sent(
  conn: CustomTCPConnection ref,
  data: (String val | Array[U8 val] val))
: (String val | Array[U8 val] val)
```
#### Parameters

*   conn: [CustomTCPConnection](.-customnet-CustomTCPConnection) ref
*   data: ([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)

#### Returns

* ([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)

---

### sentv

```pony
fun ref sentv(
  conn: CustomTCPConnection ref,
  data: ByteSeqIter val)
: ByteSeqIter val
```
#### Parameters

*   conn: [CustomTCPConnection](.-customnet-CustomTCPConnection) ref
*   data: [ByteSeqIter](builtin-ByteSeqIter) val

#### Returns

* [ByteSeqIter](builtin-ByteSeqIter) val

---

## Private Functions

### _update_consumers

```pony
fun ref _update_consumers(
  topic_consumers: HashMap[String val, Array[KafkaConsumer tag] val, HashEq[String val] val] val)
: None val
```
#### Parameters

*   topic_consumers: [HashMap](collections-HashMap)\[[String](builtin-String) val, [Array](builtin-Array)\[[KafkaConsumer](pony-kafka-KafkaConsumer) tag\] val, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val

#### Returns

* [None](builtin-None) val

---

### _get_conf

```pony
fun box _get_conf()
: KafkaConfig val
```

#### Returns

* [KafkaConfig](pony-kafka-KafkaConfig) val

---

### _get_client

```pony
fun box _get_client()
: KafkaClient tag
```

#### Returns

* [KafkaClient](pony-kafka-KafkaClient) tag

---

### _get_name

```pony
fun box _get_name()
: String val
```

#### Returns

* [String](builtin-String) val

---

### _update_consumer_message_handler

```pony
fun ref _update_consumer_message_handler(
  topic: String val,
  consumer_handler: KafkaConsumerMessageHandler val)
: None val
```
#### Parameters

*   topic: [String](builtin-String) val
*   consumer_handler: [KafkaConsumerMessageHandler](pony-kafka-KafkaConsumerMessageHandler) val

#### Returns

* [None](builtin-None) val

---

### _consumer_pause

```pony
fun ref _consumer_pause(
  conn: KafkaBrokerConnection ref,
  topic: String val,
  partition_id: I32 val)
: None val
```
#### Parameters

*   conn: [KafkaBrokerConnection](pony-kafka-KafkaBrokerConnection) ref
*   topic: [String](builtin-String) val
*   partition_id: [I32](builtin-I32) val

#### Returns

* [None](builtin-None) val

---

### _consumer_pause_all

```pony
fun ref _consumer_pause_all(
  conn: KafkaBrokerConnection ref)
: None val
```
#### Parameters

*   conn: [KafkaBrokerConnection](pony-kafka-KafkaBrokerConnection) ref

#### Returns

* [None](builtin-None) val

---

### _consumer_resume

```pony
fun ref _consumer_resume(
  conn: KafkaBrokerConnection ref,
  topic: String val,
  partition_id: I32 val)
: None val
```
#### Parameters

*   conn: [KafkaBrokerConnection](pony-kafka-KafkaBrokerConnection) ref
*   topic: [String](builtin-String) val
*   partition_id: [I32](builtin-I32) val

#### Returns

* [None](builtin-None) val

---

### _consumer_resume_all

```pony
fun ref _consumer_resume_all(
  conn: KafkaBrokerConnection ref)
: None val
```
#### Parameters

*   conn: [KafkaBrokerConnection](pony-kafka-KafkaBrokerConnection) ref

#### Returns

* [None](builtin-None) val

---

### _next_correlation_id

```pony
fun ref _next_correlation_id()
: I32 val
```

#### Returns

* [I32](builtin-I32) val

---

### _maybe_process_pending_buffer

```pony
fun ref _maybe_process_pending_buffer(
  conn: KafkaBrokerConnection ref)
: None val
```
#### Parameters

*   conn: [KafkaBrokerConnection](pony-kafka-KafkaBrokerConnection) ref

#### Returns

* [None](builtin-None) val

---

### _send_pending_messages

```pony
fun ref _send_pending_messages(
  conn: KafkaBrokerConnection ref)
: None val
```
#### Parameters

*   conn: [KafkaBrokerConnection](pony-kafka-KafkaBrokerConnection) ref

#### Returns

* [None](builtin-None) val

---

### _write_to_network

```pony
fun box _write_to_network(
  conn: KafkaBrokerConnection ref,
  data: ByteSeqIter val)
: None val
```
#### Parameters

*   conn: [KafkaBrokerConnection](pony-kafka-KafkaBrokerConnection) ref
*   data: [ByteSeqIter](builtin-ByteSeqIter) val

#### Returns

* [None](builtin-None) val

---

### _update_metadata

```pony
fun ref _update_metadata(
  meta: _KafkaMetadata val,
  conn: KafkaBrokerConnection ref)
: None val
```
#### Parameters

*   meta: [_KafkaMetadata](pony-kafka-_KafkaMetadata) val
*   conn: [KafkaBrokerConnection](pony-kafka-KafkaBrokerConnection) ref

#### Returns

* [None](builtin-None) val

---

### _leader_change_msgs

```pony
fun ref _leader_change_msgs(
  meta: _KafkaMetadata val,
  topic: String val,
  partition_id: I32 val,
  msgs: HashMap[I32 val, Array[ProducerKafkaMessage val] iso, HashEq[I32 val] val] val,
  request_offset: I64 val,
  conn: KafkaBrokerConnection ref)
: None val
```
#### Parameters

*   meta: [_KafkaMetadata](pony-kafka-_KafkaMetadata) val
*   topic: [String](builtin-String) val
*   partition_id: [I32](builtin-I32) val
*   msgs: [HashMap](collections-HashMap)\[[I32](builtin-I32) val, [Array](builtin-Array)\[[ProducerKafkaMessage](pony-kafka-ProducerKafkaMessage) val\] iso, [HashEq](collections-HashEq)\[[I32](builtin-I32) val\] val\] val
*   request_offset: [I64](builtin-I64) val
*   conn: [KafkaBrokerConnection](pony-kafka-KafkaBrokerConnection) ref

#### Returns

* [None](builtin-None) val

---

### _leader_change_throttle_ack

```pony
fun ref _leader_change_throttle_ack(
  topics_to_throttle: HashMap[String val, HashSet[I32 val, HashEq[I32 val] val] iso, HashEq[String val] val] val,
  conn: KafkaBrokerConnection ref)
: None val
```
#### Parameters

*   topics_to_throttle: [HashMap](collections-HashMap)\[[String](builtin-String) val, [HashSet](collections-HashSet)\[[I32](builtin-I32) val, [HashEq](collections-HashEq)\[[I32](builtin-I32) val\] val\] iso, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val
*   conn: [KafkaBrokerConnection](pony-kafka-KafkaBrokerConnection) ref

#### Returns

* [None](builtin-None) val

---

