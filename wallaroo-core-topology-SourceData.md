# SourceData

```pony
class val SourceData
```

## Constructors

### create

```pony
new val create(
  id': U128 val,
  b: SourceBuilderBuilder val,
  r: RunnerBuilder val,
  default_source_route_builder: RouteBuilder val,
  s: SourceListenerBuilderBuilder val,
  pre_state_target_ids': Array[U128 val] val = seq)
: SourceData val^
```
#### Parameters

*   id': [U128](builtin-U128) val
*   b: [SourceBuilderBuilder](wallaroo-core-source-SourceBuilderBuilder) val
*   r: [RunnerBuilder](wallaroo-core-topology-RunnerBuilder) val
*   default_source_route_builder: [RouteBuilder](wallaroo-core-routing-RouteBuilder) val
*   s: [SourceListenerBuilderBuilder](wallaroo-core-source-SourceListenerBuilderBuilder) val
*   pre_state_target_ids': [Array](builtin-Array)\[[U128](builtin-U128) val\] val = seq

#### Returns

* [SourceData](wallaroo-core-topology-SourceData) val^

---

## Public Functions

### builder

```pony
fun box builder()
: SourceBuilderBuilder val
```

#### Returns

* [SourceBuilderBuilder](wallaroo-core-source-SourceBuilderBuilder) val

---

### runner_builder

```pony
fun box runner_builder()
: RunnerBuilder val
```

#### Returns

* [RunnerBuilder](wallaroo-core-topology-RunnerBuilder) val

---

### route_builder

```pony
fun box route_builder()
: RouteBuilder val
```

#### Returns

* [RouteBuilder](wallaroo-core-routing-RouteBuilder) val

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
  r: Router val)
: Router val
```
#### Parameters

*   r: [Router](wallaroo-core-topology-Router) val

#### Returns

* [Router](wallaroo-core-topology-Router) val

---

### source_listener_builder_builder

```pony
fun box source_listener_builder_builder()
: SourceListenerBuilderBuilder val
```

#### Returns

* [SourceListenerBuilderBuilder](wallaroo-core-source-SourceListenerBuilderBuilder) val

---

