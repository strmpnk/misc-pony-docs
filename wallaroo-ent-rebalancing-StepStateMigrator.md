# StepStateMigrator

```pony
primitive val StepStateMigrator
```

## Constructors

### create

```pony
new val create()
: StepStateMigrator val^
```

#### Returns

* [StepStateMigrator](wallaroo-ent-rebalancing-StepStateMigrator) val^

---

## Public Functions

### receive_state

```pony
fun box receive_state(
  runner: Runner ref,
  state: (String val | Array[U8 val] val))
: None val
```
#### Parameters

*   runner: [Runner](wallaroo-core-topology-Runner) ref
*   state: ([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)

#### Returns

* [None](builtin-None) val

---

### send_state_to_neighbour

```pony
fun box send_state_to_neighbour(
  runner: Runner ref,
  neighbour: Step tag)
: None val
```
#### Parameters

*   runner: [Runner](wallaroo-core-topology-Runner) ref
*   neighbour: [Step](wallaroo-core-topology-Step) tag

#### Returns

* [None](builtin-None) val

---

### send_state\[K: ([Hashable](collections-Hashable) val & [Equatable](builtin-Equatable)\[K\] val)\]

```pony
fun box send_state[K: (Hashable val & Equatable[K] val)](
  runner: Runner ref,
  id: U128 val,
  boundary: OutgoingBoundary tag,
  state_name: String val,
  key: K)
: None val
```
#### Parameters

*   runner: [Runner](wallaroo-core-topology-Runner) ref
*   id: [U128](builtin-U128) val
*   boundary: [OutgoingBoundary](wallaroo-core-boundary-OutgoingBoundary) tag
*   state_name: [String](builtin-String) val
*   key: K

#### Returns

* [None](builtin-None) val

---

### eq

```pony
fun box eq(
  that: StepStateMigrator val)
: Bool val
```
#### Parameters

*   that: [StepStateMigrator](wallaroo-ent-rebalancing-StepStateMigrator) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: StepStateMigrator val)
: Bool val
```
#### Parameters

*   that: [StepStateMigrator](wallaroo-ent-rebalancing-StepStateMigrator) val

#### Returns

* [Bool](builtin-Bool) val

---

