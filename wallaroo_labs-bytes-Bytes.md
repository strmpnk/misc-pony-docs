# Bytes

```pony
primitive val Bytes
```

## Constructors

### create

```pony
new val create()
: Bytes val^
```

#### Returns

* [Bytes](wallaroo_labs-bytes-Bytes) val^

---

## Public Functions

### length_encode

```pony
fun box length_encode(
  data: (String val | Array[U8 val] val))
: Array[(String val | Array[U8 val] val)] val
```
#### Parameters

*   data: ([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)

#### Returns

* [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val

---

### to_u16

```pony
fun box to_u16(
  high: U8 val,
  low: U8 val)
: U16 val
```
#### Parameters

*   high: [U8](builtin-U8) val
*   low: [U8](builtin-U8) val

#### Returns

* [U16](builtin-U16) val

---

### to_u32

```pony
fun box to_u32(
  a: U8 val,
  b: U8 val,
  c: U8 val,
  d: U8 val)
: U32 val
```
#### Parameters

*   a: [U8](builtin-U8) val
*   b: [U8](builtin-U8) val
*   c: [U8](builtin-U8) val
*   d: [U8](builtin-U8) val

#### Returns

* [U32](builtin-U32) val

---

### to_u64

```pony
fun box to_u64(
  a: U8 val,
  b: U8 val,
  c: U8 val,
  d: U8 val,
  e: U8 val,
  f: U8 val,
  g: U8 val,
  h: U8 val)
: U64 val
```
#### Parameters

*   a: [U8](builtin-U8) val
*   b: [U8](builtin-U8) val
*   c: [U8](builtin-U8) val
*   d: [U8](builtin-U8) val
*   e: [U8](builtin-U8) val
*   f: [U8](builtin-U8) val
*   g: [U8](builtin-U8) val
*   h: [U8](builtin-U8) val

#### Returns

* [U64](builtin-U64) val

---

### to_f32

```pony
fun box to_f32(
  a: U8 val,
  b: U8 val,
  c: U8 val,
  d: U8 val)
: F32 val
```
#### Parameters

*   a: [U8](builtin-U8) val
*   b: [U8](builtin-U8) val
*   c: [U8](builtin-U8) val
*   d: [U8](builtin-U8) val

#### Returns

* [F32](builtin-F32) val

---

### to_f64

```pony
fun box to_f64(
  a: U8 val,
  b: U8 val,
  c: U8 val,
  d: U8 val,
  e: U8 val,
  f: U8 val,
  g: U8 val,
  h: U8 val)
: F64 val
```
#### Parameters

*   a: [U8](builtin-U8) val
*   b: [U8](builtin-U8) val
*   c: [U8](builtin-U8) val
*   d: [U8](builtin-U8) val
*   e: [U8](builtin-U8) val
*   f: [U8](builtin-U8) val
*   g: [U8](builtin-U8) val
*   h: [U8](builtin-U8) val

#### Returns

* [F64](builtin-F64) val

---

### from_u16

```pony
fun box from_u16(
  u16: U16 val,
  arr: Array[U8 val] iso = seq)
: Array[U8 val] iso^
```
#### Parameters

*   u16: [U16](builtin-U16) val
*   arr: [Array](builtin-Array)\[[U8](builtin-U8) val\] iso = seq

#### Returns

* [Array](builtin-Array)\[[U8](builtin-U8) val\] iso^

---

### from_u32

```pony
fun box from_u32(
  u32: U32 val,
  arr: Array[U8 val] iso = seq)
: Array[U8 val] iso^
```
#### Parameters

*   u32: [U32](builtin-U32) val
*   arr: [Array](builtin-Array)\[[U8](builtin-U8) val\] iso = seq

#### Returns

* [Array](builtin-Array)\[[U8](builtin-U8) val\] iso^

---

### from_u64

```pony
fun box from_u64(
  u64: U64 val,
  arr: Array[U8 val] iso = seq)
: Array[U8 val] iso^
```
#### Parameters

*   u64: [U64](builtin-U64) val
*   arr: [Array](builtin-Array)\[[U8](builtin-U8) val\] iso = seq

#### Returns

* [Array](builtin-Array)\[[U8](builtin-U8) val\] iso^

---

### from_f32

```pony
fun box from_f32(
  f32: F32 val,
  arr: Array[U8 val] iso = seq)
: Array[U8 val] iso^
```
#### Parameters

*   f32: [F32](builtin-F32) val
*   arr: [Array](builtin-Array)\[[U8](builtin-U8) val\] iso = seq

#### Returns

* [Array](builtin-Array)\[[U8](builtin-U8) val\] iso^

---

### from_f64

```pony
fun box from_f64(
  f64: F64 val,
  arr: Array[U8 val] iso = seq)
: Array[U8 val] iso^
```
#### Parameters

*   f64: [F64](builtin-F64) val
*   arr: [Array](builtin-Array)\[[U8](builtin-U8) val\] iso = seq

#### Returns

* [Array](builtin-Array)\[[U8](builtin-U8) val\] iso^

---

### u16_from_idx

```pony
fun box u16_from_idx(
  idx: USize val,
  arr: Array[U8 val] ref)
: U16 val ?
```
#### Parameters

*   idx: [USize](builtin-USize) val
*   arr: [Array](builtin-Array)\[[U8](builtin-U8) val\] ref

#### Returns

* [U16](builtin-U16) val ?

---

### u32_from_idx

```pony
fun box u32_from_idx(
  idx: USize val,
  arr: Array[U8 val] ref)
: U32 val ?
```
#### Parameters

*   idx: [USize](builtin-USize) val
*   arr: [Array](builtin-Array)\[[U8](builtin-U8) val\] ref

#### Returns

* [U32](builtin-U32) val ?

---

### u64_from_idx

```pony
fun box u64_from_idx(
  idx: USize val,
  arr: Array[U8 val] ref)
: U64 val ?
```
#### Parameters

*   idx: [USize](builtin-USize) val
*   arr: [Array](builtin-Array)\[[U8](builtin-U8) val\] ref

#### Returns

* [U64](builtin-U64) val ?

---

### eq

```pony
fun box eq(
  that: Bytes val)
: Bool val
```
#### Parameters

*   that: [Bytes](wallaroo_labs-bytes-Bytes) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: Bytes val)
: Bool val
```
#### Parameters

*   that: [Bytes](wallaroo_labs-bytes-Bytes) val

#### Returns

* [Bool](builtin-Bool) val

---

