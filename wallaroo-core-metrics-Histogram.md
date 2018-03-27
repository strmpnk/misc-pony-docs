# Histogram

A Histogram where each value is counted into the bin of its next power of 2
value. e.g. 3->bin:4, 4->bin:4, 5->bin:8, etc.

In addition to the histogram itself, we are storing the min, max_value
and total number of values seen (throughput) for reporting.


```pony
class ref Histogram
```

## Constructors

### create

```pony
new iso create()
: Histogram iso^
```

#### Returns

* [Histogram](wallaroo-core-metrics-Histogram) iso^

---

## Public Functions

### get_idx

Return the power of 2 of the value to be used as its index in the histogram


```pony
fun box get_idx(
  v: U64 val)
: USize val
```
#### Parameters

*   v: [U64](builtin-U64) val

#### Returns

* [USize](builtin-USize) val

---

### get

Get the count at the i-th bin, raising an error if the index is out
of bounds.


```pony
fun box get(
  i: USize val)
: U64 val ?
```
#### Parameters

*   i: [USize](builtin-USize) val

#### Returns

* [U64](builtin-U64) val ?

---

### size

```pony
fun box size()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### counts

```pony
fun box counts()
: this->Array[U64 val] ref
```

#### Returns

* this->[Array](builtin-Array)\[[U64](builtin-U64) val\] ref

---

### min

```pony
fun box min()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### max

```pony
fun box max()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### apply

Count a U64 value in the correct bin in the histogram


```pony
fun ref apply(
  v: U64 val)
: None val
```
#### Parameters

*   v: [U64](builtin-U64) val

#### Returns

* [None](builtin-None) val

---

