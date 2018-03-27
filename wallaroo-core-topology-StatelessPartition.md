# StatelessPartition

```pony
primitive val StatelessPartition
```

## Constructors

### create

```pony
new val create()
: StatelessPartition val^
```

#### Returns

* [StatelessPartition](wallaroo-core-topology-StatelessPartition) val^

---

## Public Functions

### pre_stateless_data

```pony
fun box pre_stateless_data(
  pipeline_name: String val,
  partition_id: U128 val,
  workers: Array[String val] val,
  threads_per_worker: USize val)
: PreStatelessData val ?
```
#### Parameters

*   pipeline_name: [String](builtin-String) val
*   partition_id: [U128](builtin-U128) val
*   workers: [Array](builtin-Array)\[[String](builtin-String) val\] val
*   threads_per_worker: [USize](builtin-USize) val

#### Returns

* [PreStatelessData](wallaroo-core-topology-PreStatelessData) val ?

---

### eq

```pony
fun box eq(
  that: StatelessPartition val)
: Bool val
```
#### Parameters

*   that: [StatelessPartition](wallaroo-core-topology-StatelessPartition) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: StatelessPartition val)
: Bool val
```
#### Parameters

*   that: [StatelessPartition](wallaroo-core-topology-StatelessPartition) val

#### Returns

* [Bool](builtin-Bool) val

---

