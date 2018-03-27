# KafkaSourceListenerNotify\[In: [Any](builtin-Any) val\]

```pony
class ref KafkaSourceListenerNotify[In: Any val]
```

## Constructors

### create

```pony
new iso create(
  builder: SourceBuilder val,
  event_log: EventLog tag,
  auth: AmbientAuth val,
  target_router: Router val)
: KafkaSourceListenerNotify[In] iso^
```
#### Parameters

*   builder: [SourceBuilder](wallaroo-core-source-SourceBuilder) val
*   event_log: [EventLog](wallaroo-ent-recovery-EventLog) tag
*   auth: [AmbientAuth](builtin-AmbientAuth) val
*   target_router: [Router](wallaroo-core-topology-Router) val

#### Returns

* [KafkaSourceListenerNotify](wallaroo-core-source-kafka_source-KafkaSourceListenerNotify)\[In\] iso^

---

## Public Functions

### build_source

```pony
fun ref build_source(
  env: Env val)
: KafkaSourceNotify[In] iso^ ?
```
#### Parameters

*   env: [Env](builtin-Env) val

#### Returns

* [KafkaSourceNotify](wallaroo-core-source-kafka_source-KafkaSourceNotify)\[In\] iso^ ?

---

### update_router

```pony
fun ref update_router(
  router: Router val)
: None val
```
#### Parameters

*   router: [Router](wallaroo-core-topology-Router) val

#### Returns

* [None](builtin-None) val

---

