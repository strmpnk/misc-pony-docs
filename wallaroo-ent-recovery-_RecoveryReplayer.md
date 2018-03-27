# _RecoveryReplayer

This only exists for testability.


```pony
interface ref _RecoveryReplayer
```

## Private Functions

### _boundary_reconnected

```pony
fun ref _boundary_reconnected(
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

### _wait_for_reconnections

```pony
fun ref _wait_for_reconnections(
  expected_boundaries: HashMap[String val, USize val, HashEq[String val] val] box,
  reconnected_boundaries: HashMap[String val, HashSet[U128 val, HashIs[U128 val] val] ref, HashEq[String val] val] ref)
: None val
```
#### Parameters

*   expected_boundaries: [HashMap](collections-HashMap)\[[String](builtin-String) val, [USize](builtin-USize) val, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] box
*   reconnected_boundaries: [HashMap](collections-HashMap)\[[String](builtin-String) val, [HashSet](collections-HashSet)\[[U128](builtin-U128) val, [HashIs](collections-HashIs)\[[U128](builtin-U128) val\] val\] ref, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] ref

#### Returns

* [None](builtin-None) val

---

### _start_replay_phase

```pony
fun ref _start_replay_phase(
  expected_boundaries: HashMap[String val, USize val, HashEq[String val] val] box)
: None val
```
#### Parameters

*   expected_boundaries: [HashMap](collections-HashMap)\[[String](builtin-String) val, [USize](builtin-USize) val, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] box

#### Returns

* [None](builtin-None) val

---

### _end_replay_phase

```pony
fun ref _end_replay_phase()
: None val
```

#### Returns

* [None](builtin-None) val

---

### _clear_deduplication_lists

```pony
fun ref _clear_deduplication_lists()
: None val
```

#### Returns

* [None](builtin-None) val

---

