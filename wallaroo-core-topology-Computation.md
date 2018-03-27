# Computation\[In: [Any](builtin-Any) val, Out: [Any](builtin-Any) val\]

```pony
interface ref Computation[In: Any val, Out: Any val] is
  BasicComputation ref
```

#### Implements

* [BasicComputation](wallaroo-core-topology-BasicComputation) ref

---

## Public Functions

### apply

```pony
fun box apply(
  input: In)
: (Out | Array[Out] val | None val)
```
#### Parameters

*   input: In

#### Returns

* (Out | [Array](builtin-Array)\[Out\] val | [None](builtin-None) val)

---

### name

```pony
fun box name()
: String val
```

#### Returns

* [String](builtin-String) val

---

