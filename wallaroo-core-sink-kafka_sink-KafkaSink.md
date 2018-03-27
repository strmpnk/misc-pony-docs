# KafkaSink

```pony
actor tag KafkaSink is
  Consumer tag,
  KafkaClientManager ref,
  KafkaProducer ref
```

#### Implements

* [Consumer](wallaroo-core-common-Consumer) tag
* [KafkaClientManager](pony-kafka-KafkaClientManager) ref
* [KafkaProducer](pony-kafka-KafkaProducer) ref

---

## Constructors

### create

```pony
new tag create(
  encoder_wrapper: KafkaEncoderWrapper val,
  metrics_reporter: MetricsReporter iso,
  conf: KafkaConfig val,
  auth: (AmbientAuth val | NetAuth val | TCPAuth val | 
    TCPConnectAuth val))
: KafkaSink tag^
```
#### Parameters

*   encoder_wrapper: [KafkaEncoderWrapper](wallaroo-core-sink-kafka_sink-KafkaEncoderWrapper) val
*   metrics_reporter: [MetricsReporter](wallaroo-core-metrics-MetricsReporter) iso
*   conf: [KafkaConfig](pony-kafka-KafkaConfig) val
*   auth: ([AmbientAuth](builtin-AmbientAuth) val | [NetAuth](net-NetAuth) val | [TCPAuth](net-TCPAuth) val | 
    [TCPConnectAuth](net-TCPConnectAuth) val)

#### Returns

* [KafkaSink](wallaroo-core-sink-kafka_sink-KafkaSink) tag^

---

## Public Behaviours

### kafka_client_error

```pony
be kafka_client_error(
  error_report: KafkaErrorReport val)
```
#### Parameters

*   error_report: [KafkaErrorReport](pony-kafka-KafkaErrorReport) val

---

### receive_kafka_topics_partitions

```pony
be receive_kafka_topics_partitions(
  new_topic_partitions: HashMap[String val, ((KafkaConsumeOnly val | KafkaProduceOnly val | KafkaProduceAndConsume val) , HashSet[I32 val, HashEq[I32 val] val] ref), HashEq[String val] val] val)
```
#### Parameters

*   new_topic_partitions: [HashMap](collections-HashMap)\[[String](builtin-String) val, (([KafkaConsumeOnly](pony-kafka-KafkaConsumeOnly) val | [KafkaProduceOnly](pony-kafka-KafkaProduceOnly) val | [KafkaProduceAndConsume](pony-kafka-KafkaProduceAndConsume) val) , [HashSet](collections-HashSet)\[[I32](builtin-I32) val, [HashEq](collections-HashEq)\[[I32](builtin-I32) val\] val\] ref), [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val

---

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

### application_begin_reporting

```pony
be application_begin_reporting(
  initializer: LocalTopologyInitializer tag)
```
#### Parameters

*   initializer: [LocalTopologyInitializer](wallaroo-core-initialization-LocalTopologyInitializer) tag

---

### application_created

```pony
be application_created(
  initializer: LocalTopologyInitializer tag,
  omni_router: OmniRouter val)
```
#### Parameters

*   initializer: [LocalTopologyInitializer](wallaroo-core-initialization-LocalTopologyInitializer) tag
*   omni_router: [OmniRouter](wallaroo-core-topology-OmniRouter) val

---

### application_initialized

```pony
be application_initialized(
  initializer: LocalTopologyInitializer tag)
```
#### Parameters

*   initializer: [LocalTopologyInitializer](wallaroo-core-initialization-LocalTopologyInitializer) tag

---

### application_ready_to_work

```pony
be application_ready_to_work(
  initializer: LocalTopologyInitializer tag)
```
#### Parameters

*   initializer: [LocalTopologyInitializer](wallaroo-core-initialization-LocalTopologyInitializer) tag

---

### request_ack

```pony
be request_ack()
```

---

### register_producer

```pony
be register_producer(
  producer: Producer tag)
```
#### Parameters

*   producer: [Producer](wallaroo-core-common-Producer) tag

---

### unregister_producer

```pony
be unregister_producer(
  producer: Producer tag)
```
#### Parameters

*   producer: [Producer](wallaroo-core-common-Producer) tag

---

### run\[D: [Any](builtin-Any) val\]

```pony
be run[D: Any val](
  metric_name: String val,
  pipeline_time_spent: U64 val,
  data: D,
  i_producer: Producer tag,
  msg_uid: U128 val,
  frac_ids: (Array[U32 val] val | None val),
  i_seq_id: U64 val,
  i_route_id: U64 val,
  latest_ts: U64 val,
  metrics_id: U16 val,
  worker_ingress_ts: U64 val)
```
#### Parameters

*   metric_name: [String](builtin-String) val
*   pipeline_time_spent: [U64](builtin-U64) val
*   data: D
*   i_producer: [Producer](wallaroo-core-common-Producer) tag
*   msg_uid: [U128](builtin-U128) val
*   frac_ids: ([Array](builtin-Array)\[[U32](builtin-U32) val\] val | [None](builtin-None) val)
*   i_seq_id: [U64](builtin-U64) val
*   i_route_id: [U64](builtin-U64) val
*   latest_ts: [U64](builtin-U64) val
*   metrics_id: [U16](builtin-U16) val
*   worker_ingress_ts: [U64](builtin-U64) val

---

### replay_run\[D: [Any](builtin-Any) val\]

```pony
be replay_run[D: Any val](
  metric_name: String val,
  pipeline_time_spent: U64 val,
  data: D,
  i_producer: Producer tag,
  msg_uid: U128 val,
  frac_ids: (Array[U32 val] val | None val),
  i_seq_id: U64 val,
  i_route_id: U64 val,
  latest_ts: U64 val,
  metrics_id: U16 val,
  worker_ingress_ts: U64 val)
```
#### Parameters

*   metric_name: [String](builtin-String) val
*   pipeline_time_spent: [U64](builtin-U64) val
*   data: D
*   i_producer: [Producer](wallaroo-core-common-Producer) tag
*   msg_uid: [U128](builtin-U128) val
*   frac_ids: ([Array](builtin-Array)\[[U32](builtin-U32) val\] val | [None](builtin-None) val)
*   i_seq_id: [U64](builtin-U64) val
*   i_route_id: [U64](builtin-U64) val
*   latest_ts: [U64](builtin-U64) val
*   metrics_id: [U16](builtin-U16) val
*   worker_ingress_ts: [U64](builtin-U64) val

---

### receive_state

```pony
be receive_state(
  state: (String val | Array[U8 val] val))
```
#### Parameters

*   state: ([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)

---

### dispose

```pony
be dispose()
```

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

### _mute_upstreams

```pony
fun ref _mute_upstreams()
: None val
```

#### Returns

* [None](builtin-None) val

---

### _unmute_upstreams

```pony
fun ref _unmute_upstreams()
: None val
```

#### Returns

* [None](builtin-None) val

---

### _next_tracking_id

```pony
fun ref _next_tracking_id(
  i_producer: Producer tag,
  i_route_id: U64 val,
  i_seq_id: U64 val)
: (U64 val | None val)
```
#### Parameters

*   i_producer: [Producer](wallaroo-core-common-Producer) tag
*   i_route_id: [U64](builtin-U64) val
*   i_seq_id: [U64](builtin-U64) val

#### Returns

* ([U64](builtin-U64) val | [None](builtin-None) val)

---

