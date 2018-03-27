# _StepGenerator

```pony
primitive val _StepGenerator
```

## Constructors

### create

```pony
new val create()
: _StepGenerator val^
```

#### Returns

* [_StepGenerator](wallaroo-core-topology-_StepGenerator) val^

---

## Public Functions

### apply

```pony
fun box apply(
  event_log: EventLog tag,
  recovery_replayer: RecoveryReplayer tag)
: Step tag
```
#### Parameters

*   event_log: [EventLog](wallaroo-ent-recovery-EventLog) tag
*   recovery_replayer: [RecoveryReplayer](wallaroo-ent-recovery-RecoveryReplayer) tag

#### Returns

* [Step](wallaroo-core-topology-Step) tag

---

### eq

```pony
fun box eq(
  that: _StepGenerator val)
: Bool val
```
#### Parameters

*   that: [_StepGenerator](wallaroo-core-topology-_StepGenerator) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: _StepGenerator val)
: Bool val
```
#### Parameters

*   that: [_StepGenerator](wallaroo-core-topology-_StepGenerator) val

#### Returns

* [Bool](builtin-Bool) val

---

