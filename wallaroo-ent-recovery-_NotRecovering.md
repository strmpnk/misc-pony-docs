# _NotRecovering

```pony
class ref _NotRecovering is
  _RecoveryPhase ref
```

#### Implements

* [_RecoveryPhase](wallaroo-ent-recovery-_RecoveryPhase) ref

---

## Constructors

### create

```pony
new iso create()
: _NotRecovering iso^
```

#### Returns

* [_NotRecovering](wallaroo-ent-recovery-_NotRecovering) iso^

---

## Public Functions

### start_recovery

```pony
fun box start_recovery(
  workers: Array[String val] val,
  recovery: Recovery ref)
: None val
```
#### Parameters

*   workers: [Array](builtin-Array)\[[String](builtin-String) val\] val
*   recovery: [Recovery](wallaroo-ent-recovery-Recovery) ref

#### Returns

* [None](builtin-None) val

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

### start_msg_replay

```pony
fun ref start_msg_replay()
: None val ?
```

#### Returns

* [None](builtin-None) val ?

---

### msg_replay_finished

```pony
fun ref msg_replay_finished()
: None val ?
```

#### Returns

* [None](builtin-None) val ?

---

