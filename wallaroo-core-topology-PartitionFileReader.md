# PartitionFileReader

```pony
primitive val PartitionFileReader
```

## Constructors

### create

```pony
new val create()
: PartitionFileReader val^
```

#### Returns

* [PartitionFileReader](wallaroo-core-topology-PartitionFileReader) val^

---

## Public Functions

### apply

```pony
fun box apply(
  filename: String val,
  auth: AmbientAuth val)
: Array[(String val , USize val)] val
```
#### Parameters

*   filename: [String](builtin-String) val
*   auth: [AmbientAuth](builtin-AmbientAuth) val

#### Returns

* [Array](builtin-Array)\[([String](builtin-String) val , [USize](builtin-USize) val)\] val

---

### eq

```pony
fun box eq(
  that: PartitionFileReader val)
: Bool val
```
#### Parameters

*   that: [PartitionFileReader](wallaroo-core-topology-PartitionFileReader) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: PartitionFileReader val)
: Bool val
```
#### Parameters

*   that: [PartitionFileReader](wallaroo-core-topology-PartitionFileReader) val

#### Returns

* [Bool](builtin-Bool) val

---

