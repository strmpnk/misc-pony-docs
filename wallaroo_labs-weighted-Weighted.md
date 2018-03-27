# Weighted\[V: [Any](builtin-Any) val\]

```pony
primitive val Weighted[V: Any val]
```

## Constructors

### create

```pony
new val create()
: Weighted[V] val^
```

#### Returns

* [Weighted](wallaroo_labs-weighted-Weighted)\[V\] val^

---

## Public Functions

### apply

```pony
fun box apply(
  unsorted_items: Array[(V , USize val)] val,
  bucket_count: USize val)
: Array[Array[V] ref] val ?
```
#### Parameters

*   unsorted_items: [Array](builtin-Array)\[(V , [USize](builtin-USize) val)\] val
*   bucket_count: [USize](builtin-USize) val

#### Returns

* [Array](builtin-Array)\[[Array](builtin-Array)\[V\] ref\] val ?

---

### sort

```pony
fun box sort(
  a: Array[(V , USize val)] val)
: Array[(V , USize val)] ref ?
```
#### Parameters

*   a: [Array](builtin-Array)\[(V , [USize](builtin-USize) val)\] val

#### Returns

* [Array](builtin-Array)\[(V , [USize](builtin-USize) val)\] ref ?

---

### eq

```pony
fun box eq(
  that: Weighted[V] val)
: Bool val
```
#### Parameters

*   that: [Weighted](wallaroo_labs-weighted-Weighted)\[V\] val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: Weighted[V] val)
: Bool val
```
#### Parameters

*   that: [Weighted](wallaroo_labs-weighted-Weighted)\[V\] val

#### Returns

* [Bool](builtin-Bool) val

---

## Private Functions

### _lowest_weight_idx

```pony
fun box _lowest_weight_idx(
  bucket_weights: Array[USize val] ref)
: USize val ?
```
#### Parameters

*   bucket_weights: [Array](builtin-Array)\[[USize](builtin-USize) val\] ref

#### Returns

* [USize](builtin-USize) val ?

---

### _lowest_sort_idx

```pony
fun box _lowest_sort_idx(
  a: Array[(V , USize val)] ref)
: USize val ?
```
#### Parameters

*   a: [Array](builtin-Array)\[(V , [USize](builtin-USize) val)\] ref

#### Returns

* [USize](builtin-USize) val ?

---

