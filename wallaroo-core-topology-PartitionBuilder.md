# PartitionBuilder

```pony
trait val PartitionBuilder
```

## Public Functions

### state_subpartition

```pony
fun box state_subpartition(
  workers: (String val | Array[String val] val))
: StateSubpartition val
```
#### Parameters

*   workers: ([String](builtin-String) val | [Array](builtin-Array)\[[String](builtin-String) val\] val)

#### Returns

* [StateSubpartition](wallaroo-core-topology-StateSubpartition) val

---

### partition_addresses

```pony
fun box partition_addresses(
  workers: (String val | Array[String val] val))
: PartitionAddresses val
```
#### Parameters

*   workers: ([String](builtin-String) val | [Array](builtin-Array)\[[String](builtin-String) val\] val)

#### Returns

* [PartitionAddresses](wallaroo-core-topology-PartitionAddresses) val

---

### state_name

```pony
fun box state_name()
: String val
```

#### Returns

* [String](builtin-String) val

---

### is_multi

```pony
fun box is_multi()
: Bool val
```

#### Returns

* [Bool](builtin-Bool) val

---

