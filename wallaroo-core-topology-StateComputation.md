# StateComputation\[In: [Any](builtin-Any) val, Out: [Any](builtin-Any) val, S: [State](wallaroo-core-state-State) ref\]

```pony
interface ref StateComputation[In: Any val, Out: Any val, S: State ref] is
  BasicComputation ref
```

#### Implements

* [BasicComputation](wallaroo-core-topology-BasicComputation) ref

---

## Public Functions

### apply

```pony
fun box apply(
  input: In,
  sc_repo: StateChangeRepository[S] ref,
  state: S)
: ((Out | Array[Out] val | None val) , (StateChange[S] ref | DirectStateChange val | None val))
```
#### Parameters

*   input: In
*   sc_repo: [StateChangeRepository](wallaroo-core-state-StateChangeRepository)\[S\] ref
*   state: S

#### Returns

* ((Out | [Array](builtin-Array)\[Out\] val | [None](builtin-None) val) , ([StateChange](wallaroo-core-state-StateChange)\[S\] ref | [DirectStateChange](wallaroo-core-state-DirectStateChange) val | [None](builtin-None) val))

---

### name

```pony
fun box name()
: String val
```

#### Returns

* [String](builtin-String) val

---

### state_change_builders

```pony
fun box state_change_builders()
: Array[StateChangeBuilder[S] val] val
```

#### Returns

* [Array](builtin-Array)\[[StateChangeBuilder](wallaroo-core-state-StateChangeBuilder)\[S\] val\] val

---

