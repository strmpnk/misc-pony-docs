# StateRunnerBuilder\[S: [State](wallaroo-core-state-State) ref\]

```pony
class val StateRunnerBuilder[S: State ref] is
  RunnerBuilder val
```

#### Implements

* [RunnerBuilder](wallaroo-core-topology-RunnerBuilder) val

---

## Constructors

### create

```pony
new val create(
  state_builder: StateBuilder[S] val,
  state_name': String val,
  state_change_builders: Array[StateChangeBuilder[S] val] val,
  route_builder': RouteBuilder val = seq)
: StateRunnerBuilder[S] val^
```
#### Parameters

*   state_builder: [StateBuilder](wallaroo-core-topology-StateBuilder)\[S\] val
*   state_name': [String](builtin-String) val
*   state_change_builders: [Array](builtin-Array)\[[StateChangeBuilder](wallaroo-core-state-StateChangeBuilder)\[S\] val\] val
*   route_builder': [RouteBuilder](wallaroo-core-routing-RouteBuilder) val = seq

#### Returns

* [StateRunnerBuilder](wallaroo-core-topology-StateRunnerBuilder)\[S\] val^

---

## Public Functions

### apply

```pony
fun box apply(
  event_log: EventLog tag,
  auth: AmbientAuth val,
  next_runner: (Runner iso | None val) = seq,
  router: (Router val | None val) = seq,
  pre_state_target_ids': Array[U128 val] val = seq)
: Runner iso^
```
#### Parameters

*   event_log: [EventLog](wallaroo-ent-recovery-EventLog) tag
*   auth: [AmbientAuth](builtin-AmbientAuth) val
*   next_runner: ([Runner](wallaroo-core-topology-Runner) iso | [None](builtin-None) val) = seq
*   router: ([Router](wallaroo-core-topology-Router) val | [None](builtin-None) val) = seq
*   pre_state_target_ids': [Array](builtin-Array)\[[U128](builtin-U128) val\] val = seq

#### Returns

* [Runner](wallaroo-core-topology-Runner) iso^

---

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

### is_stateful

```pony
fun box is_stateful()
: Bool val
```

#### Returns

* [Bool](builtin-Bool) val

---

### id

```pony
fun box id()
: U128 val
```

#### Returns

* [U128](builtin-U128) val

---

### route_builder

```pony
fun box route_builder()
: RouteBuilder val
```

#### Returns

* [RouteBuilder](wallaroo-core-routing-RouteBuilder) val

---

### forward_route_builder

```pony
fun box forward_route_builder()
: RouteBuilder val
```

#### Returns

* [RouteBuilder](wallaroo-core-routing-RouteBuilder) val

---

### is_prestate

```pony
fun box is_prestate()
: Bool val
```

#### Returns

* [Bool](builtin-Bool) val

---

### is_stateless_parallel

```pony
fun box is_stateless_parallel()
: Bool val
```

#### Returns

* [Bool](builtin-Bool) val

---

### is_multi

```pony
fun box is_multi()
: Bool val
```

#### Returns

* [Bool](builtin-Bool) val

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

