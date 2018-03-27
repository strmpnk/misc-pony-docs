# _BoundaryMsgReplay

```pony
class ref _BoundaryMsgReplay is
  _RecoveryPhase ref
```

#### Implements

* [_RecoveryPhase](wallaroo-ent-recovery-_RecoveryPhase) ref

---

## Constructors

### create

```pony
new ref create(
  workers: Array[String val] val,
  recovery_replayer: (RecoveryReplayer tag | None val),
  recovery: Recovery ref)
: _BoundaryMsgReplay ref^
```
#### Parameters

*   workers: [Array](builtin-Array)\[[String](builtin-String) val\] val
*   recovery_replayer: ([RecoveryReplayer](wallaroo-ent-recovery-RecoveryReplayer) tag | [None](builtin-None) val)
*   recovery: [Recovery](wallaroo-ent-recovery-Recovery) ref

#### Returns

* [_BoundaryMsgReplay](wallaroo-ent-recovery-_BoundaryMsgReplay) ref^

---

## Public Functions

### start_msg_replay

```pony
fun ref start_msg_replay()
: None val
```

#### Returns

* [None](builtin-None) val

---

### msg_replay_finished

```pony
fun ref msg_replay_finished()
: None val
```

#### Returns

* [None](builtin-None) val

---

### start_recovery

```pony
fun box start_recovery(
  workers: Array[String val] val,
  recovery: Recovery ref)
: None val ?
```
#### Parameters

*   workers: [Array](builtin-Array)\[[String](builtin-String) val\] val
*   recovery: [Recovery](wallaroo-ent-recovery-Recovery) ref

#### Returns

* [None](builtin-None) val ?

---

### start_log_replay

```pony
fun box start_log_replay(
  event_log: EventLog tag)
: None val ?
```
#### Parameters

*   event_log: [EventLog](wallaroo-ent-recovery-EventLog) tag

#### Returns

* [None](builtin-None) val ?

---

### log_replay_finished

```pony
fun ref log_replay_finished()
: None val ?
```

#### Returns

* [None](builtin-None) val ?

---

