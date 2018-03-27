# KafkaSourceListenerBuilder\[In: [Any](builtin-Any) val\]

```pony
class val KafkaSourceListenerBuilder[In: Any val]
```

## Constructors

### create

```pony
new val create(
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
: KafkaSourceListenerBuilder[In] val^
```
#### Parameters

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

* [KafkaSourceListenerBuilder](wallaroo-core-source-kafka_source-KafkaSourceListenerBuilder)\[In\] val^

---

## Public Functions

### apply

```pony
fun box apply(
  env: Env val)
: SourceListener tag
```
#### Parameters

*   env: [Env](builtin-Env) val

#### Returns

* [SourceListener](wallaroo-core-source-SourceListener) tag

---

