# ArrayHelpers\[V: V\]

```pony
primitive val ArrayHelpers[V: V]
```

## Constructors

### create

```pony
new val create()
: ArrayHelpers[V] val^
```

#### Returns

* [ArrayHelpers](wallaroo_labs-collection_helpers-ArrayHelpers)\[V\] val^

---

## Public Functions

### forall

```pony
fun box forall(
  arr: Array[V] box,
  pred: {(box->V!): Bool}[V] ref)
: Bool val
```
#### Parameters

*   arr: [Array](builtin-Array)\[V\] box
*   pred: {(box->V!): Bool}[V] ref

#### Returns

* [Bool](builtin-Bool) val

---

### some

```pony
fun box some(
  arr: Array[V] box,
  pred: {(box->V!): Bool}[V] ref)
: Bool val
```
#### Parameters

*   arr: [Array](builtin-Array)\[V\] box
*   pred: {(box->V!): Bool}[V] ref

#### Returns

* [Bool](builtin-Bool) val

---

### sorted\[A: [Comparable](builtin-Comparable)\[A\] val\]

```pony
fun box sorted[A: Comparable[A] val](
  arr: Array[A] val)
: Array[A] ref
```
#### Parameters

*   arr: [Array](builtin-Array)\[A\] val

#### Returns

* [Array](builtin-Array)\[A\] ref

---

### contains\[A: [Equatable](builtin-Equatable)\[A\] #read\]

```pony
fun box contains[A: Equatable[A] #read](
  arr: Array[A] box,
  v: A)
: Bool val
```
#### Parameters

*   arr: [Array](builtin-Array)\[A\] box
*   v: A

#### Returns

* [Bool](builtin-Bool) val

---

### eq\[A: [Equatable](builtin-Equatable)\[A\] #read\]

```pony
fun box eq[A: Equatable[A] #read](
  arr1: Array[A] box,
  arr2: Array[A] box)
: Bool val
```
#### Parameters

*   arr1: [Array](builtin-Array)\[A\] box
*   arr2: [Array](builtin-Array)\[A\] box

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: ArrayHelpers[V] val)
: Bool val
```
#### Parameters

*   that: [ArrayHelpers](wallaroo_labs-collection_helpers-ArrayHelpers)\[V\] val

#### Returns

* [Bool](builtin-Bool) val

---

