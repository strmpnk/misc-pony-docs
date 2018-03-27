# StepLogEntryReplayer

```pony
primitive val StepLogEntryReplayer
```

## Constructors

### create

```pony
new val create()
: StepLogEntryReplayer val^
```

#### Returns

* [StepLogEntryReplayer](wallaroo-ent-recovery-StepLogEntryReplayer) val^

---

## Public Functions

### apply

```pony
fun box apply(
  runner: Runner ref,
  deduplication_list: Array[(U128 val , (Array[U32 val] val | None val))] ref,
  uid: U128 val,
  frac_ids: (Array[U32 val] val | None val),
  statechange_id: U64 val,
  payload: (String val | Array[U8 val] val),
  this_step: Step tag)
: None val
```
#### Parameters

*   runner: [Runner](wallaroo-core-topology-Runner) ref
*   deduplication_list: [Array](builtin-Array)\[([U128](builtin-U128) val , ([Array](builtin-Array)\[[U32](builtin-U32) val\] val | [None](builtin-None) val))\] ref
*   uid: [U128](builtin-U128) val
*   frac_ids: ([Array](builtin-Array)\[[U32](builtin-U32) val\] val | [None](builtin-None) val)
*   statechange_id: [U64](builtin-U64) val
*   payload: ([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)
*   this_step: [Step](wallaroo-core-topology-Step) tag

#### Returns

* [None](builtin-None) val

---

### eq

```pony
fun box eq(
  that: StepLogEntryReplayer val)
: Bool val
```
#### Parameters

*   that: [StepLogEntryReplayer](wallaroo-ent-recovery-StepLogEntryReplayer) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: StepLogEntryReplayer val)
: Bool val
```
#### Parameters

*   that: [StepLogEntryReplayer](wallaroo-ent-recovery-StepLogEntryReplayer) val

#### Returns

* [Bool](builtin-Bool) val

---

