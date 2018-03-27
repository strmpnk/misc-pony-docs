# Recovery

Phases:
  1) _NotRecovering: Waiting for start_recovery() to be called
  2) _LogReplay: Wait for EventLog to finish replaying the event logs
  3) _BoundaryMsgReplay: Wait for RecoveryReplayer to manage message replay
     from incoming boundaries.
  4) _NotRecovering: Finished recovery


```pony
actor tag Recovery
```

## Constructors

### create

```pony
new tag create(
  auth: AmbientAuth val,
  worker_name: String val,
  event_log: EventLog tag,
  recovery_replayer: (RecoveryReplayer tag | None val) = seq,
  connections: Connections tag)
: Recovery tag^
```
#### Parameters

*   auth: [AmbientAuth](builtin-AmbientAuth) val
*   worker_name: [String](builtin-String) val
*   event_log: [EventLog](wallaroo-ent-recovery-EventLog) tag
*   recovery_replayer: ([RecoveryReplayer](wallaroo-ent-recovery-RecoveryReplayer) tag | [None](builtin-None) val) = seq
*   connections: [Connections](wallaroo-ent-network-Connections) tag

#### Returns

* [Recovery](wallaroo-ent-recovery-Recovery) tag^

---

## Public Behaviours

### start_recovery

```pony
be start_recovery(
  initializer: LocalTopologyInitializer tag,
  workers: Array[String val] val)
```
#### Parameters

*   initializer: [LocalTopologyInitializer](wallaroo-core-initialization-LocalTopologyInitializer) tag
*   workers: [Array](builtin-Array)\[[String](builtin-String) val\] val

---

### log_replay_finished

```pony
be log_replay_finished()
```

---

### recovery_replay_finished

```pony
be recovery_replay_finished()
```

---

## Private Functions

### _start_log_replay

```pony
fun ref _start_log_replay(
  workers: Array[String val] val)
: None val
```
#### Parameters

*   workers: [Array](builtin-Array)\[[String](builtin-String) val\] val

#### Returns

* [None](builtin-None) val

---

### _end_log_replay

```pony
fun ref _end_log_replay(
  workers: Array[String val] val)
: None val
```
#### Parameters

*   workers: [Array](builtin-Array)\[[String](builtin-String) val\] val

#### Returns

* [None](builtin-None) val

---

### _start_msg_replay

```pony
fun ref _start_msg_replay(
  workers: Array[String val] val)
: None val
```
#### Parameters

*   workers: [Array](builtin-Array)\[[String](builtin-String) val\] val

#### Returns

* [None](builtin-None) val

---

### _end_recovery

```pony
fun ref _end_recovery()
: None val
```

#### Returns

* [None](builtin-None) val

---

