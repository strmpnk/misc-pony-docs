# SingleStepPartitionFunction\[In: [Any](builtin-Any) val\]

```pony
primitive val SingleStepPartitionFunction[In: Any val] is
  PartitionFunction[In, U8 val] ref
```

#### Implements

* [PartitionFunction](wallaroo-core-topology-PartitionFunction)\[In, [U8](builtin-U8) val\] ref

---

## Constructors

### create

```pony
new val create()
: SingleStepPartitionFunction[In] val^
```

#### Returns

* [SingleStepPartitionFunction](wallaroo-core-topology-SingleStepPartitionFunction)\[In\] val^

---

## Public Functions

### apply

```pony
fun box apply(
  input: In)
: U8 val
```
#### Parameters

*   input: In

#### Returns

* [U8](builtin-U8) val

---

### eq

```pony
fun box eq(
  that: SingleStepPartitionFunction[In] val)
: Bool val
```
#### Parameters

*   that: [SingleStepPartitionFunction](wallaroo-core-topology-SingleStepPartitionFunction)\[In\] val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: SingleStepPartitionFunction[In] val)
: Bool val
```
#### Parameters

*   that: [SingleStepPartitionFunction](wallaroo-core-topology-SingleStepPartitionFunction)\[In\] val

#### Returns

* [Bool](builtin-Bool) val

---

