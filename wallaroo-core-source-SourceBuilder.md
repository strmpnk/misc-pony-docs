# SourceBuilder

```pony
trait val SourceBuilder
```

## Public Functions

### name

```pony
fun box name()
: String val
```

#### Returns

* [String](builtin-String) val

---

### apply

```pony
fun box apply(
  event_log: EventLog tag,
  auth: AmbientAuth val,
  target_router: Router val,
  env: Env val)
: SourceNotify iso^
```
#### Parameters

*   event_log: [EventLog](wallaroo-ent-recovery-EventLog) tag
*   auth: [AmbientAuth](builtin-AmbientAuth) val
*   target_router: [Router](wallaroo-core-topology-Router) val
*   env: [Env](builtin-Env) val

#### Returns

* [SourceNotify](wallaroo-core-source-SourceNotify) iso^

---

### update_router

```pony
fun val update_router(
  router: Router val)
: SourceBuilder val
```
#### Parameters

*   router: [Router](wallaroo-core-topology-Router) val

#### Returns

* [SourceBuilder](wallaroo-core-source-SourceBuilder) val

---

