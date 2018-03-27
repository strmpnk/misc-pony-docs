# StepBuilder

```pony
class val StepBuilder
```

## Constructors

### create

```pony
new val create(
  app_name: String val,
  worker_name: String val,
  pipeline_name': String val,
  r: RunnerBuilder val,
  id': U128 val,
  is_stateful': Bool val = seq,
  pre_state_target_ids': Array[U128 val] val = seq,
  forward_route_builder': RouteBuilder val = seq)
: StepBuilder val^
```
#### Parameters

*   app_name: [String](builtin-String) val
*   worker_name: [String](builtin-String) val
*   pipeline_name': [String](builtin-String) val
*   r: [RunnerBuilder](wallaroo-core-topology-RunnerBuilder) val
*   id': [U128](builtin-U128) val
*   is_stateful': [Bool](builtin-Bool) val = seq
*   pre_state_target_ids': [Array](builtin-Array)\[[U128](builtin-U128) val\] val = seq
*   forward_route_builder': [RouteBuilder](wallaroo-core-routing-RouteBuilder) val = seq

#### Returns

* [StepBuilder](wallaroo-core-topology-StepBuilder) val^

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

### in_route_builder

```pony
fun box in_route_builder()
: (RouteBuilder val | None val)
```

#### Returns

* ([RouteBuilder](wallaroo-core-routing-RouteBuilder) val | [None](builtin-None) val)

---

### clone_router_and_set_input_type

```pony
fun box clone_router_and_set_input_type(
  r: Router val)
: Router val
```
#### Parameters

*   r: [Router](wallaroo-core-topology-Router) val

#### Returns

* [Router](wallaroo-core-topology-Router) val

---

### apply

```pony
fun box apply(
  next: Router val,
  metrics_conn: MetricsSink tag,
  event_log: EventLog tag,
  recovery_replayer: RecoveryReplayer tag,
  auth: AmbientAuth val,
  outgoing_boundaries: HashMap[String val, OutgoingBoundary tag, HashEq[String val] val] val,
  router: Router val = seq,
  omni_router: OmniRouter val = seq)
: Step tag
```
#### Parameters

*   next: [Router](wallaroo-core-topology-Router) val
*   metrics_conn: [MetricsSink](wallaroo-core-metrics-MetricsSink) tag
*   event_log: [EventLog](wallaroo-ent-recovery-EventLog) tag
*   recovery_replayer: [RecoveryReplayer](wallaroo-ent-recovery-RecoveryReplayer) tag
*   auth: [AmbientAuth](builtin-AmbientAuth) val
*   outgoing_boundaries: [HashMap](collections-HashMap)\[[String](builtin-String) val, [OutgoingBoundary](wallaroo-core-boundary-OutgoingBoundary) tag, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val
*   router: [Router](wallaroo-core-topology-Router) val = seq
*   omni_router: [OmniRouter](wallaroo-core-topology-OmniRouter) val = seq

#### Returns

* [Step](wallaroo-core-topology-Step) tag

---

