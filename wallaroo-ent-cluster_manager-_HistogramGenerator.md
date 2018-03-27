# _HistogramGenerator

```pony
primitive val _HistogramGenerator
```

## Constructors

### create

```pony
new val create()
: _HistogramGenerator val^
```

#### Returns

* [_HistogramGenerator](wallaroo-ent-cluster_manager-_HistogramGenerator) val^

---

## Public Functions

### apply

```pony
fun box apply(
  size: U64 val)
: Histogram val
```
#### Parameters

*   size: [U64](builtin-U64) val

#### Returns

* [Histogram](wallaroo-core-metrics-Histogram) val

---

### eq

```pony
fun box eq(
  that: _HistogramGenerator val)
: Bool val
```
#### Parameters

*   that: [_HistogramGenerator](wallaroo-ent-cluster_manager-_HistogramGenerator) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: _HistogramGenerator val)
: Bool val
```
#### Parameters

*   that: [_HistogramGenerator](wallaroo-ent-cluster_manager-_HistogramGenerator) val

#### Returns

* [Bool](builtin-Bool) val

---

