# MapEquality\[K: ([Hashable](collections-Hashable) #read & [Equatable](builtin-Equatable)\[K\] #read), V: [Equatable](builtin-Equatable)\[V\] #read\]

```pony
primitive val MapEquality[K: (Hashable #read & Equatable[K] #read), V: Equatable[V] #read]
```

## Constructors

### create

```pony
new val create()
: MapEquality[K, V] val^
```

#### Returns

* [MapEquality](wallaroo_labs-equality-MapEquality)\[K, V\] val^

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
  that: MapEquality[K, V] val)
: Bool val
```
#### Parameters

*   that: [MapEquality](wallaroo_labs-equality-MapEquality)\[K, V\] val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: MapEquality[K, V] val)
: Bool val
```
#### Parameters

*   that: [MapEquality](wallaroo_labs-equality-MapEquality)\[K, V\] val

#### Returns

* [Bool](builtin-Bool) val

---

