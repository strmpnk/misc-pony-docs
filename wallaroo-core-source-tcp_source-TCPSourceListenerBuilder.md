# TCPSourceListenerBuilder

```pony
class val TCPSourceListenerBuilder
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
  host: String val = seq,
  service: String val = seq)
: TCPSourceListenerBuilder val^
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
*   host: [String](builtin-String) val = seq
*   service: [String](builtin-String) val = seq

#### Returns

* [TCPSourceListenerBuilder](wallaroo-core-source-tcp_source-TCPSourceListenerBuilder) val^

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

