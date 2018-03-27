# _Replay

```pony
class ref _Replay is
  _ReplayPhase ref
```

#### Implements

* [_ReplayPhase](wallaroo-ent-recovery-_ReplayPhase) ref

---

## Constructors

### create

```pony
new ref create(
  expected_boundaries: HashMap[String val, USize val, HashEq[String val] val] box,
  replayer: _RecoveryReplayer ref,
  data_receivers: DataReceivers tag)
: _Replay ref^
```
#### Parameters

*   expected_boundaries: [HashMap](collections-HashMap)\[[String](builtin-String) val, [USize](builtin-USize) val, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] box
*   replayer: [_RecoveryReplayer](wallaroo-ent-recovery-_RecoveryReplayer) ref
*   data_receivers: [DataReceivers](wallaroo-ent-data_receiver-DataReceivers) tag

#### Returns

* [_Replay](wallaroo-ent-recovery-_Replay) ref^

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

### add_reconnected_boundary

```pony
fun ref add_reconnected_boundary(
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

## Private Functions

### _all_replays_complete

```pony
fun box _all_replays_complete(
  replay_completes: HashMap[String val, HashSet[U128 val, HashIs[U128 val] val] ref, HashEq[String val] val] ref)
: Bool val
```
#### Parameters

*   replay_completes: [HashMap](collections-HashMap)\[[String](builtin-String) val, [HashSet](collections-HashSet)\[[U128](builtin-U128) val, [HashIs](collections-HashIs)\[[U128](builtin-U128) val\] val\] ref, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] ref

#### Returns

* [Bool](builtin-Bool) val

---

