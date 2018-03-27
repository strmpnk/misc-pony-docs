# PreStateData

```pony
class val PreStateData
```

## Constructors

### create

```pony
new val create(
  runner_builder: RunnerBuilder val,
  t_ids: Array[U128 val] val)
: PreStateData val^
```
#### Parameters

*   runner_builder: [RunnerBuilder](wallaroo-core-topology-RunnerBuilder) val
*   t_ids: [Array](builtin-Array)\[[U128](builtin-U128) val\] val

#### Returns

* [PreStateData](wallaroo-core-topology-PreStateData) val^

---

## Public Functions

### state_name

```pony
fun box state_name()
: String val
```

#### Returns

* [String](builtin-String) val

---

### pre_state_name

```pony
fun box pre_state_name()
: String val
```

#### Returns

* [String](builtin-String) val

---

### target_ids

```pony
fun box target_ids()
: Array[U128 val] val
```

#### Returns

* [Array](builtin-Array)\[[U128](builtin-U128) val\] val

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

