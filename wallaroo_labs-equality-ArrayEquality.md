# ArrayEquality\[V: [Equatable](builtin-Equatable)\[V\] #read\]

```pony
primitive val ArrayEquality[V: Equatable[V] #read]
```

## Constructors

### create

```pony
new val create()
: ArrayEquality[V] val^
```

#### Returns

* [ArrayEquality](wallaroo_labs-equality-ArrayEquality)\[V\] val^

---

## Public Functions

### apply

```pony
fun box apply(
  a1: Array[V] box,
  a2: Array[V] box)
: Bool val
```
#### Parameters

*   a1: [Array](builtin-Array)\[V\] box
*   a2: [Array](builtin-Array)\[V\] box

#### Returns

* [Bool](builtin-Bool) val

---

### eq

```pony
fun box eq(
  that: ArrayEquality[V] val)
: Bool val
```
#### Parameters

*   that: [ArrayEquality](wallaroo_labs-equality-ArrayEquality)\[V\] val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: ArrayEquality[V] val)
: Bool val
```
#### Parameters

*   that: [ArrayEquality](wallaroo_labs-equality-ArrayEquality)\[V\] val

#### Returns

* [Bool](builtin-Bool) val

---

