# MetricsSinkNotify

```pony
class ref MetricsSinkNotify is
  _MetricsSinkNotify ref
```

#### Implements

* [_MetricsSinkNotify](wallaroo-core-metrics-_MetricsSinkNotify) ref

---

## Constructors

### create

```pony
new iso create(
  metrics_conn: MetricsSink tag,
  name: String val,
  application_name: String val,
  worker_name: String val)
: MetricsSinkNotify iso^
```
#### Parameters

*   metrics_conn: [MetricsSink](wallaroo-core-metrics-MetricsSink) tag
*   name: [String](builtin-String) val
*   application_name: [String](builtin-String) val
*   worker_name: [String](builtin-String) val

#### Returns

* [MetricsSinkNotify](wallaroo-core-metrics-MetricsSinkNotify) iso^

---

## Public Functions

### connected

```pony
fun ref connected(
  sock: MetricsSink ref)
: None val
```
#### Parameters

*   sock: [MetricsSink](wallaroo-core-metrics-MetricsSink) ref

#### Returns

* [None](builtin-None) val

---

### connect_failed

```pony
fun ref connect_failed(
  conn: MetricsSink ref)
: None val
```
#### Parameters

*   conn: [MetricsSink](wallaroo-core-metrics-MetricsSink) ref

#### Returns

* [None](builtin-None) val

---

### closed

```pony
fun ref closed(
  conn: MetricsSink ref)
: None val
```
#### Parameters

*   conn: [MetricsSink](wallaroo-core-metrics-MetricsSink) ref

#### Returns

* [None](builtin-None) val

---

### throttled

```pony
fun ref throttled(
  sock: MetricsSink ref)
: None val
```
#### Parameters

*   sock: [MetricsSink](wallaroo-core-metrics-MetricsSink) ref

#### Returns

* [None](builtin-None) val

---

### unthrottled

```pony
fun ref unthrottled(
  sock: MetricsSink ref)
: None val
```
#### Parameters

*   sock: [MetricsSink](wallaroo-core-metrics-MetricsSink) ref

#### Returns

* [None](builtin-None) val

---

### connecting

```pony
fun ref connecting(
  conn: MetricsSink ref,
  count: U32 val)
: None val
```
#### Parameters

*   conn: [MetricsSink](wallaroo-core-metrics-MetricsSink) ref
*   count: [U32](builtin-U32) val

#### Returns

* [None](builtin-None) val

---

### accepted

```pony
fun ref accepted(
  conn: MetricsSink ref)
: None val
```
#### Parameters

*   conn: [MetricsSink](wallaroo-core-metrics-MetricsSink) ref

#### Returns

* [None](builtin-None) val

---

### sent

```pony
fun ref sent(
  conn: MetricsSink ref,
  data: (String val | Array[U8 val] val))
: (String val | Array[U8 val] val)
```
#### Parameters

*   conn: [MetricsSink](wallaroo-core-metrics-MetricsSink) ref
*   data: ([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)

#### Returns

* ([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)

---

### sentv

```pony
fun ref sentv(
  conn: MetricsSink ref,
  data: ByteSeqIter val)
: ByteSeqIter val
```
#### Parameters

*   conn: [MetricsSink](wallaroo-core-metrics-MetricsSink) ref
*   data: [ByteSeqIter](builtin-ByteSeqIter) val

#### Returns

* [ByteSeqIter](builtin-ByteSeqIter) val

---

### received

```pony
fun ref received(
  conn: MetricsSink ref,
  data: Array[U8 val] iso,
  times: USize val)
: Bool val
```
#### Parameters

*   conn: [MetricsSink](wallaroo-core-metrics-MetricsSink) ref
*   data: [Array](builtin-Array)\[[U8](builtin-U8) val\] iso
*   times: [USize](builtin-USize) val

#### Returns

* [Bool](builtin-Bool) val

---

### expect

```pony
fun ref expect(
  conn: MetricsSink ref,
  qty: USize val)
: USize val
```
#### Parameters

*   conn: [MetricsSink](wallaroo-core-metrics-MetricsSink) ref
*   qty: [USize](builtin-USize) val

#### Returns

* [USize](builtin-USize) val

---

