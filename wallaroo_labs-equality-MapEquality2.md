# MapEquality2\[K: ([Hashable](collections-Hashable) #read & [Equatable](builtin-Equatable)\[K\] #read), V1: [Equatable](builtin-Equatable)\[V1\] #read, V2: [Equatable](builtin-Equatable)\[V2\] #read\]

```pony
primitive val MapEquality2[K: (Hashable #read & Equatable[K] #read), V1: Equatable[V1] #read, V2: Equatable[V2] #read]
```

## Constructors

### create

```pony
new val create()
: MapEquality2[K, V1, V2] val^
```

#### Returns

* [MapEquality2](wallaroo_labs-equality-MapEquality2)\[K, V1, V2\] val^

---

## Public Functions

### apply

```pony
fun box apply(
  m1: HashMap[K, (V1 | V2), HashEq[K] val] box,
  m2: HashMap[K, (V1 | V2), HashEq[K] val] box)
: Bool val
```
#### Parameters

*   m1: [HashMap](collections-HashMap)\[K, (V1 | V2), [HashEq](collections-HashEq)\[K\] val\] box
*   m2: [HashMap](collections-HashMap)\[K, (V1 | V2), [HashEq](collections-HashEq)\[K\] val\] box

#### Returns

* [Bool](builtin-Bool) val

---

### eq

```pony
fun box eq(
  that: MapEquality2[K, V1, V2] val)
: Bool val
```
#### Parameters

*   that: [MapEquality2](wallaroo_labs-equality-MapEquality2)\[K, V1, V2\] val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: MapEquality2[K, V1, V2] val)
: Bool val
```
#### Parameters

*   that: [MapEquality2](wallaroo_labs-equality-MapEquality2)\[K, V1, V2\] val

#### Returns

* [Bool](builtin-Bool) val

---

