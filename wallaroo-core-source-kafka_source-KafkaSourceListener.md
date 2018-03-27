# KafkaSourceListener\[In: [Any](builtin-Any) val\]

```pony
actor tag KafkaSourceListener[In: Any val] is
  SourceListener tag,
  KafkaClientManager ref
```

#### Implements

* [SourceListener](wallaroo-core-source-SourceListener) tag
* [KafkaClientManager](pony-kafka-KafkaClientManager) ref

---

## Constructors

### create

```pony
new tag create(
  env: Env val,
  source_builder: SourceBuilder val,
  router: Router val,
  router_registry: RouterRegistry tag,
  route_builder: RouteBuilder val,
  outgoing_boundary_builders: HashMap[String val, OutgoingBoundaryBuilder val, HashEq[String val] val] val,
  event_log: EventLog tag,
  auth: AmbientAuth val,
  layout_initializer: LayoutInitializer tag,
  metrics_reporter: MetricsReporter iso,
  target_router: Router val = seq,
  ksco: KafkaConfigOptions val,
  tcp_auth: (AmbientAuth val | NetAuth val | TCPAuth val | 
    TCPConnectAuth val))
: KafkaSourceListener[In] tag^
```
#### Parameters

*   env: [Env](builtin-Env) val
*   source_builder: [SourceBuilder](wallaroo-core-source-SourceBuilder) val
*   router: [Router](wallaroo-core-topology-Router) val
*   router_registry: [RouterRegistry](wallaroo-ent-router_registry-RouterRegistry) tag
*   route_builder: [RouteBuilder](wallaroo-core-routing-RouteBuilder) val
*   outgoing_boundary_builders: [HashMap](collections-HashMap)\[[String](builtin-String) val, [OutgoingBoundaryBuilder](wallaroo-core-boundary-OutgoingBoundaryBuilder) val, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val
*   event_log: [EventLog](wallaroo-ent-recovery-EventLog) tag
*   auth: [AmbientAuth](builtin-AmbientAuth) val
*   layout_initializer: [LayoutInitializer](wallaroo-core-initialization-LayoutInitializer) tag
*   metrics_reporter: [MetricsReporter](wallaroo-core-metrics-MetricsReporter) iso
*   target_router: [Router](wallaroo-core-topology-Router) val = seq
*   ksco: [KafkaConfigOptions](pony-kafka-KafkaConfigOptions) val
*   tcp_auth: ([AmbientAuth](builtin-AmbientAuth) val | [NetAuth](net-NetAuth) val | [TCPAuth](net-TCPAuth) val | 
    [TCPConnectAuth](net-TCPConnectAuth) val)

#### Returns

* [KafkaSourceListener](wallaroo-core-source-kafka_source-KafkaSourceListener)\[In\] tag^

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

### update_router

```pony
be update_router(
  router: Router val)
```
#### Parameters

*   router: [Router](wallaroo-core-topology-Router) val

---

### remove_route_for

```pony
be remove_route_for(
  moving_step: Consumer tag)
```
#### Parameters

*   moving_step: [Consumer](wallaroo-core-common-Consumer) tag

---

### add_boundary_builders

```pony
be add_boundary_builders(
  boundary_builders: HashMap[String val, OutgoingBoundaryBuilder val, HashEq[String val] val] val)
```
#### Parameters

*   boundary_builders: [HashMap](collections-HashMap)\[[String](builtin-String) val, [OutgoingBoundaryBuilder](wallaroo-core-boundary-OutgoingBoundaryBuilder) val, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val

---

### update_boundary_builders

```pony
be update_boundary_builders(
  boundary_builders: HashMap[String val, OutgoingBoundaryBuilder val, HashEq[String val] val] val)
```
#### Parameters

*   boundary_builders: [HashMap](collections-HashMap)\[[String](builtin-String) val, [OutgoingBoundaryBuilder](wallaroo-core-boundary-OutgoingBoundaryBuilder) val, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val

---

### remove_boundary

```pony
be remove_boundary(
  worker: String val)
```
#### Parameters

*   worker: [String](builtin-String) val

---

### dispose

```pony
be dispose()
```

---

