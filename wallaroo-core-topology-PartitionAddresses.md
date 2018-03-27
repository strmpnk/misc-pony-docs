# PartitionAddresses

```pony
interface ref PartitionAddresses is
  Equatable[PartitionAddresses ref] ref
```

#### Implements

* [Equatable](builtin-Equatable)\[[PartitionAddresses](wallaroo-core-topology-PartitionAddresses) ref\] ref

---

## Public Functions

### apply

```pony
fun box apply(
  key: Any val)
: (ProxyAddress val | None val)
```
#### Parameters

*   key: [Any](builtin-Any) val

#### Returns

* ([ProxyAddress](wallaroo-core-topology-ProxyAddress) val | [None](builtin-None) val)

---

### update_key\[Key: ([Hashable](collections-Hashable) val & [Equatable](builtin-Equatable)\[Key\] val)\]

```pony
fun box update_key[Key: (Hashable val & Equatable[Key] val)](
  key: Key,
  pa: ProxyAddress val)
: PartitionAddresses val ?
```
#### Parameters

*   key: Key
*   pa: [ProxyAddress](wallaroo-core-topology-ProxyAddress) val

#### Returns

* [PartitionAddresses](wallaroo-core-topology-PartitionAddresses) val ?

---

### eq

```pony
fun box eq(
  that: PartitionAddresses box)
: Bool val
```
#### Parameters

*   that: [PartitionAddresses](wallaroo-core-topology-PartitionAddresses) box

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: PartitionAddresses box)
: Bool val
```
#### Parameters

*   that: [PartitionAddresses](wallaroo-core-topology-PartitionAddresses) box

#### Returns

* [Bool](builtin-Bool) val

---

