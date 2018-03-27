# KeyedPartitionAddresses\[Key: ([Hashable](collections-Hashable) val & [Equatable](builtin-Equatable)\[Key\] val)\]

```pony
class ref KeyedPartitionAddresses[Key: (Hashable val & Equatable[Key] val)]
```

## Constructors

### create

```pony
new val create(
  a: HashMap[Key, ProxyAddress val, HashEq[Key] val] val)
: KeyedPartitionAddresses[Key] val^
```
#### Parameters

*   a: [HashMap](collections-HashMap)\[Key, [ProxyAddress](wallaroo-core-topology-ProxyAddress) val, [HashEq](collections-HashEq)\[Key\] val\] val

#### Returns

* [KeyedPartitionAddresses](wallaroo-core-topology-KeyedPartitionAddresses)\[Key\] val^

---

## Public Functions

### apply

```pony
fun box apply(
  k: Any val)
: (ProxyAddress val | None val)
```
#### Parameters

*   k: [Any](builtin-Any) val

#### Returns

* ([ProxyAddress](wallaroo-core-topology-ProxyAddress) val | [None](builtin-None) val)

---

### pairs

```pony
fun box pairs()
: Iterator[(Key , ProxyAddress val)] ref
```

#### Returns

* [Iterator](builtin-Iterator)\[(Key , [ProxyAddress](wallaroo-core-topology-ProxyAddress) val)\] ref

---

### update_key\[K: ([Hashable](collections-Hashable) val & [Equatable](builtin-Equatable)\[K\] val)\]

```pony
fun box update_key[K: (Hashable val & Equatable[K] val)](
  key: K,
  pa: ProxyAddress val)
: PartitionAddresses val ?
```
#### Parameters

*   key: K
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

