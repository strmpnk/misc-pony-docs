# StepMigrationMsg

```pony
trait val StepMigrationMsg is
  ChannelMsg val
```

#### Implements

* [ChannelMsg](wallaroo-core-messages-ChannelMsg) val

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

