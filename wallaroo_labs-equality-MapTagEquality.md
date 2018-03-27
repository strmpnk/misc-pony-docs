# MapTagEquality\[K: ([Hashable](collections-Hashable) #read & [Equatable](builtin-Equatable)\[K\] #read), V: [Any](builtin-Any) tag\]

```pony
primitive val MapTagEquality[K: (Hashable #read & Equatable[K] #read), V: Any tag]
```

## Constructors

### create

```pony
new val create()
: MapTagEquality[K, V] val^
```

#### Returns

* [MapTagEquality](wallaroo_labs-equality-MapTagEquality)\[K, V\] val^

---

## Public Functions

### apply

```pony
fun box apply(
  m1: HashMap[K, V, HashEq[K] val] box,
  m2: HashMap[K, V, HashEq[K] val] box)
: Bool val
```
#### Parameters

*   m1: [HashMap](collections-HashMap)\[K, V, [HashEq](collections-HashEq)\[K\] val\] box
*   m2: [HashMap](collections-HashMap)\[K, V, [HashEq](collections-HashEq)\[K\] val\] box

#### Returns

* [Bool](builtin-Bool) val

---

### eq

```pony
fun box eq(
  that: MapTagEquality[K, V] val)
: Bool val
```
#### Parameters

*   that: [MapTagEquality](wallaroo_labs-equality-MapTagEquality)\[K, V\] val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: MapTagEquality[K, V] val)
: Bool val
```
#### Parameters

*   that: [MapTagEquality](wallaroo_labs-equality-MapTagEquality)\[K, V\] val

#### Returns

* [Bool](builtin-Bool) val

---

