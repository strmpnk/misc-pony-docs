# TCPSourceListener

# TCPSourceListener


```pony
actor tag TCPSourceListener is
  SourceListener tag
```

#### Implements

* [SourceListener](wallaroo-core-source-SourceListener) tag

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
  host: String val = seq,
  service: String val = seq,
  limit: USize val = seq,
  init_size: USize val = seq,
  max_size: USize val = seq)
: TCPSourceListener tag^
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
*   host: [String](builtin-String) val = seq
*   service: [String](builtin-String) val = seq
*   limit: [USize](builtin-USize) val = seq
*   init_size: [USize](builtin-USize) val = seq
*   max_size: [USize](builtin-USize) val = seq

#### Returns

* [TCPSourceListener](wallaroo-core-source-tcp_source-TCPSourceListener) tag^

---

## Public Behaviours

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

## Private Behaviours

### _event_notify

When we are readable, we accept new connections until none remain.


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

### _conn_closed

An accepted connection has closed. If we have dropped below the limit, try
to accept new connections.


```pony
be _conn_closed()
```

---

## Private Functions

### _accept

Accept connections as long as we have spawned fewer than our limit.


```pony
fun ref _accept(
  ns: U32 val = seq)
: None val
```
#### Parameters

*   ns: [U32](builtin-U32) val = seq

#### Returns

* [None](builtin-None) val

---

### _spawn

Spawn a new connection.


```pony
fun ref _spawn(
  ns: U32 val)
: None val
```
#### Parameters

*   ns: [U32](builtin-U32) val

#### Returns

* [None](builtin-None) val

---

### _notify_listening

Inform the notifier that we're listening.


```pony
fun ref _notify_listening()
: None val
```

#### Returns

* [None](builtin-None) val

---

### _notify_connected

```pony
fun ref _notify_connected()
: TCPSourceNotify iso^ ?
```

#### Returns

* [TCPSourceNotify](wallaroo-core-source-tcp_source-TCPSourceNotify) iso^ ?

---

### _close

Dispose of resources.


```pony
fun ref _close()
: None val
```

#### Returns

* [None](builtin-None) val

---

