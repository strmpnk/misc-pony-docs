# Partition\[In: [Any](builtin-Any) val, Key: ([Hashable](collections-Hashable) val & [Equatable](builtin-Equatable)\[Key\])\]

```pony
class val Partition[In: Any val, Key: (Hashable val & Equatable[Key])]
```

## Constructors

### create

```pony
new val create(
  f: PartitionFunction[In, Key] val,
  ks: (Array[(Key , USize val)] val | Array[Key] val))
: Partition[In, Key] val^
```
#### Parameters

*   f: [PartitionFunction](wallaroo-core-topology-PartitionFunction)\[In, Key\] val
*   ks: ([Array](builtin-Array)\[(Key , [USize](builtin-USize) val)\] val | [Array](builtin-Array)\[Key\] val)

#### Returns

* [Partition](wallaroo-core-topology-Partition)\[In, Key\] val^

---

## Public Functions

### function

```pony
fun box function()
: PartitionFunction[In, Key] val
```

#### Returns

* [PartitionFunction](wallaroo-core-topology-PartitionFunction)\[In, Key\] val

---

### keys

```pony
fun box keys()
: (Array[(Key , USize val)] val | Array[Key] val)
```

#### Returns

* ([Array](builtin-Array)\[(Key , [USize](builtin-USize) val)\] val | [Array](builtin-Array)\[Key\] val)

---

