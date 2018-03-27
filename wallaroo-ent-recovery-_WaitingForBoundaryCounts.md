# _WaitingForBoundaryCounts

```pony
class ref _WaitingForBoundaryCounts is
  _ReplayPhase ref
```

#### Implements

* [_ReplayPhase](wallaroo-ent-recovery-_ReplayPhase) ref

---

## Constructors

### create

```pony
new ref create(
  expected_workers: HashSet[String val, HashIs[String val] val] ref,
  reconnected_boundaries: HashMap[String val, HashSet[U128 val, HashIs[U128 val] val] ref, HashEq[String val] val] ref,
  replayer: _RecoveryReplayer ref)
: _WaitingForBoundaryCounts ref^
```
#### Parameters

*   expected_workers: [HashSet](collections-HashSet)\[[String](builtin-String) val, [HashIs](collections-HashIs)\[[String](builtin-String) val\] val\] ref
*   reconnected_boundaries: [HashMap](collections-HashMap)\[[String](builtin-String) val, [HashSet](collections-HashSet)\[[U128](builtin-U128) val, [HashIs](collections-HashIs)\[[U128](builtin-U128) val\] val\] ref, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] ref
*   replayer: [_RecoveryReplayer](wallaroo-ent-recovery-_RecoveryReplayer) ref

#### Returns

* [_WaitingForBoundaryCounts](wallaroo-ent-recovery-_WaitingForBoundaryCounts) ref^

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

### add_expected_boundary_count

```pony
fun ref add_expected_boundary_count(
  worker: String val,
  count: USize val)
: None val
```
#### Parameters

*   worker: [String](builtin-String) val
*   count: [USize](builtin-USize) val

#### Returns

* [None](builtin-None) val

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

