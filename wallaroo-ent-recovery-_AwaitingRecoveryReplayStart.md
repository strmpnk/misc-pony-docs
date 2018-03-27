# _AwaitingRecoveryReplayStart

```pony
class ref _AwaitingRecoveryReplayStart is
  _ReplayPhase ref
```

#### Implements

* [_ReplayPhase](wallaroo-ent-recovery-_ReplayPhase) ref

---

## Constructors

### create

```pony
new ref create(
  replayer: _RecoveryReplayer ref)
: _AwaitingRecoveryReplayStart ref^
```
#### Parameters

*   replayer: [_RecoveryReplayer](wallaroo-ent-recovery-_RecoveryReplayer) ref

#### Returns

* [_AwaitingRecoveryReplayStart](wallaroo-ent-recovery-_AwaitingRecoveryReplayStart) ref^

---

## Public Functions

### name

```pony
fun box name()
: String val
```

#### Returns

* [String](builtin-String) val

---

### add_reconnected_boundary

```pony
fun ref add_reconnected_boundary(
  worker: String val,
  boundary_step_id: U128 val)
: None val
```
#### Parameters

*   worker: [String](builtin-String) val
*   boundary_step_id: [U128](builtin-U128) val

#### Returns

* [None](builtin-None) val

---

### add_expected_boundary_count

```pony
fun ref add_expected_boundary_count(
  worker: String val,
  count: USize val)
: None val ?
```
#### Parameters

*   worker: [String](builtin-String) val
*   count: [USize](builtin-USize) val

#### Returns

* [None](builtin-None) val ?

---

### add_boundary_replay_complete

```pony
fun ref add_boundary_replay_complete(
  worker: String val,
  boundary_id: U128 val)
: None val ?
```
#### Parameters

*   worker: [String](builtin-String) val
*   boundary_id: [U128](builtin-U128) val

#### Returns

* [None](builtin-None) val ?

---

