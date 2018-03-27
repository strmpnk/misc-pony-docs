# KeyedStepMigrationMsg\[K: ([Hashable](collections-Hashable) val & [Equatable](builtin-Equatable)\[K\] val)\]

```pony
class val KeyedStepMigrationMsg[K: (Hashable val & Equatable[K] val)] is
  StepMigrationMsg val
```

#### Implements

* [StepMigrationMsg](wallaroo-core-messages-StepMigrationMsg) val

---

## Constructors

### create

```pony
new val create(
  step_id': U128 val,
  state_name': String val,
  key': K,
  state': (String val | Array[U8 val] val),
  worker': String val)
: KeyedStepMigrationMsg[K] val^
```
#### Parameters

*   step_id': [U128](builtin-U128) val
*   state_name': [String](builtin-String) val
*   key': K
*   state': ([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)
*   worker': [String](builtin-String) val

#### Returns

* [KeyedStepMigrationMsg](wallaroo-core-messages-KeyedStepMigrationMsg)\[K\] val^

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

### step_id

```pony
fun box step_id()
: U128 val
```

#### Returns

* [U128](builtin-U128) val

---

### state

```pony
fun box state()
: (String val | Array[U8 val] val)
```

#### Returns

* ([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)

---

### worker

```pony
fun box worker()
: String val
```

#### Returns

* [String](builtin-String) val

---

### update_router_registry

```pony
fun box update_router_registry(
  router_registry: RouterRegistry tag,
  target: Consumer tag)
: None val
```
#### Parameters

*   router_registry: [RouterRegistry](wallaroo-ent-router_registry-RouterRegistry) tag
*   target: [Consumer](wallaroo-core-common-Consumer) tag

#### Returns

* [None](builtin-None) val

---

