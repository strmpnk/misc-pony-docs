# StepStateSnapshotter

```pony
primitive val StepStateSnapshotter
```

## Constructors

### create

```pony
new val create()
: StepStateSnapshotter val^
```

#### Returns

* [StepStateSnapshotter](wallaroo-ent-recovery-StepStateSnapshotter) val^

---

## Public Functions

### apply

```pony
fun box apply(
  runner: Runner ref,
  id: U128 val,
  seq_id_generator: StepSeqIdGenerator ref,
  event_log: EventLog tag,
  wb: Writer ref = seq)
: None val
```
#### Parameters

*   runner: [Runner](wallaroo-core-topology-Runner) ref
*   id: [U128](builtin-U128) val
*   seq_id_generator: [StepSeqIdGenerator](wallaroo-core-topology-StepSeqIdGenerator) ref
*   event_log: [EventLog](wallaroo-ent-recovery-EventLog) tag
*   wb: [Writer](buffered-Writer) ref = seq

#### Returns

* [None](builtin-None) val

---

### eq

```pony
fun box eq(
  that: StepStateSnapshotter val)
: Bool val
```
#### Parameters

*   that: [StepStateSnapshotter](wallaroo-ent-recovery-StepStateSnapshotter) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: StepStateSnapshotter val)
: Bool val
```
#### Parameters

*   that: [StepStateSnapshotter](wallaroo-ent-recovery-StepStateSnapshotter) val

#### Returns

* [Bool](builtin-Bool) val

---

