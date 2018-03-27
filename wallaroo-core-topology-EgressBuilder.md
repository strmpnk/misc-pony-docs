# EgressBuilder

```pony
class val EgressBuilder
```

## Constructors

### create

```pony
new val create(
  pipeline_name': String val,
  id': U128 val,
  sink_builder: (SinkBuilder val | None val) = seq,
  proxy_addr: (ProxyAddress val | None val) = seq)
: EgressBuilder val^
```
#### Parameters

*   pipeline_name': [String](builtin-String) val
*   id': [U128](builtin-U128) val
*   sink_builder: ([SinkBuilder](wallaroo-core-sink-SinkBuilder) val | [None](builtin-None) val) = seq
*   proxy_addr: ([ProxyAddress](wallaroo-core-topology-ProxyAddress) val | [None](builtin-None) val) = seq

#### Returns

* [EgressBuilder](wallaroo-core-topology-EgressBuilder) val^

---

## Public Functions

### name

```pony
fun box name()
: String val
```

#### Returns

* [String](builtin-String) val

---

### state_name

```pony
fun box state_name()
: String val
```

#### Returns

* [String](builtin-String) val

---

### pipeline_name

```pony
fun box pipeline_name()
: String val
```

#### Returns

* [String](builtin-String) val

---

### id

```pony
fun box id()
: U128 val
```

#### Returns

* [U128](builtin-U128) val

---

### pre_state_target_ids

```pony
fun box pre_state_target_ids()
: Array[U128 val] val
```

#### Returns

* [Array](builtin-Array)\[[U128](builtin-U128) val\] val

---

### is_prestate

```pony
fun box is_prestate()
: Bool val
```

#### Returns

* [Bool](builtin-Bool) val

---

### is_stateful

```pony
fun box is_stateful()
: Bool val
```

#### Returns

* [Bool](builtin-Bool) val

---

### is_partitioned

```pony
fun box is_partitioned()
: Bool val
```

#### Returns

* [Bool](builtin-Bool) val

---

### forward_route_builder

```pony
fun box forward_route_builder()
: RouteBuilder val
```

#### Returns

* [RouteBuilder](wallaroo-core-routing-RouteBuilder) val

---

### clone_router_and_set_input_type

```pony
fun box clone_router_and_set_input_type(
  r: Router val,
  dr: (Router val | None val) = seq)
: Router val
```
#### Parameters

*   r: [Router](wallaroo-core-topology-Router) val
*   dr: ([Router](wallaroo-core-topology-Router) val | [None](builtin-None) val) = seq

#### Returns

* [Router](wallaroo-core-topology-Router) val

---

### target_address

```pony
fun box target_address()
: (ProxyAddress val | PartitionAddresses val | None val)
```

#### Returns

* ([ProxyAddress](wallaroo-core-topology-ProxyAddress) val | [PartitionAddresses](wallaroo-core-topology-PartitionAddresses) val | [None](builtin-None) val)

---

### apply

```pony
fun box apply(
  worker_name: String val,
  reporter: MetricsReporter ref,
  env: Env val,
  auth: AmbientAuth val,
  proxies: HashMap[String val, OutgoingBoundary tag, HashEq[String val] val] val = seq)
: Consumer tag ?
```
#### Parameters

*   worker_name: [String](builtin-String) val
*   reporter: [MetricsReporter](wallaroo-core-metrics-MetricsReporter) ref
*   env: [Env](builtin-Env) val
*   auth: [AmbientAuth](builtin-AmbientAuth) val
*   proxies: [HashMap](collections-HashMap)\[[String](builtin-String) val, [OutgoingBoundary](wallaroo-core-boundary-OutgoingBoundary) tag, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val = seq

#### Returns

* [Consumer](wallaroo-core-common-Consumer) tag ?

---

