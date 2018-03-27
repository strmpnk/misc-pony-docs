# SetHelpers\[V: V\]

```pony
primitive val SetHelpers[V: V]
```

## Constructors

### create

```pony
new val create()
: SetHelpers[V] val^
```

#### Returns

* [SetHelpers](wallaroo_labs-collection_helpers-SetHelpers)\[V\] val^

---

## Public Functions

### forall

```pony
fun box forall(
  s: HashSet[V, HashIs[V!] val] box,
  pred: {(box->V!): Bool}[V] ref)
: Bool val
```
#### Parameters

*   s: [HashSet](collections-HashSet)\[V, [HashIs](collections-HashIs)\[V!\] val\] box
*   pred: {(box->V!): Bool}[V] ref

#### Returns

* [Bool](builtin-Bool) val

---

### some

```pony
fun box some(
  s: HashSet[V, HashIs[V!] val] box,
  pred: {(box->V!): Bool}[V] ref)
: Bool val
```
#### Parameters

*   s: [HashSet](collections-HashSet)\[V, [HashIs](collections-HashIs)\[V!\] val\] box
*   pred: {(box->V!): Bool}[V] ref

#### Returns

* [Bool](builtin-Bool) val

---

### contains\[A: [Equatable](builtin-Equatable)\[A\] #read\]

```pony
fun box contains[A: Equatable[A] #read](
  arr: HashSet[A, HashIs[A!] val] box,
  v: A)
: Bool val
```
#### Parameters

*   arr: [HashSet](collections-HashSet)\[A, [HashIs](collections-HashIs)\[A!\] val\] box
*   v: A

#### Returns

* [Bool](builtin-Bool) val

---

### eq

```pony
fun box eq(
  that: SetHelpers[V] val)
: Bool val
```
#### Parameters

*   that: [SetHelpers](wallaroo_labs-collection_helpers-SetHelpers)\[V\] val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: SetHelpers[V] val)
: Bool val
```
#### Parameters

*   that: [SetHelpers](wallaroo_labs-collection_helpers-SetHelpers)\[V\] val

#### Returns

* [Bool](builtin-Bool) val

---

