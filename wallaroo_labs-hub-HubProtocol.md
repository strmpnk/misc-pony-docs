# HubProtocol

```pony
primitive val HubProtocol
```

## Constructors

### create

```pony
new val create()
: HubProtocol val^
```

#### Returns

* [HubProtocol](wallaroo_labs-hub-HubProtocol) val^

---

## Public Functions

### connect

```pony
fun box connect(
  wb: Writer ref = seq)
: Array[(String val | Array[U8 val] val)] val
```
#### Parameters

*   wb: [Writer](buffered-Writer) ref = seq

#### Returns

* [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val

---

### join_metrics

```pony
fun box join_metrics(
  topic: String val,
  worker_name: String val,
  wb: Writer ref = seq)
: Array[(String val | Array[U8 val] val)] val
```
#### Parameters

*   topic: [String](builtin-String) val
*   worker_name: [String](builtin-String) val
*   wb: [Writer](buffered-Writer) ref = seq

#### Returns

* [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val

---

### join

```pony
fun box join(
  topic: String val,
  wb: Writer ref = seq)
: Array[(String val | Array[U8 val] val)] val
```
#### Parameters

*   topic: [String](builtin-String) val
*   wb: [Writer](buffered-Writer) ref = seq

#### Returns

* [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val

---

### payload

```pony
fun box payload(
  event: String val,
  topic: String val,
  data: Array[(String val | Array[U8 val] val)] val,
  wb: Writer ref)
: None val
```
#### Parameters

*   event: [String](builtin-String) val
*   topic: [String](builtin-String) val
*   data: [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val
*   wb: [Writer](buffered-Writer) ref

#### Returns

* [None](builtin-None) val

---

### payload_into_array

```pony
fun box payload_into_array(
  event: String val,
  topic: String val,
  data: Array[U8 val] iso)
: Array[(String val | Array[U8 val] val)] val
```
#### Parameters

*   event: [String](builtin-String) val
*   topic: [String](builtin-String) val
*   data: [Array](builtin-Array)\[[U8](builtin-U8) val\] iso

#### Returns

* [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val

---

### metrics

```pony
fun box metrics(
  name: String val,
  category: String val,
  pipeline_name: String val,
  worker_name: String val,
  id: U16 val,
  histogram: Histogram val,
  period: U64 val,
  period_ends_at: U64 val,
  wb: Writer ref)
: None val
```
#### Parameters

*   name: [String](builtin-String) val
*   category: [String](builtin-String) val
*   pipeline_name: [String](builtin-String) val
*   worker_name: [String](builtin-String) val
*   id: [U16](builtin-U16) val
*   histogram: [Histogram](wallaroo-core-metrics-Histogram) val
*   period: [U64](builtin-U64) val
*   period_ends_at: [U64](builtin-U64) val
*   wb: [Writer](buffered-Writer) ref

#### Returns

* [None](builtin-None) val

---

### eq

```pony
fun box eq(
  that: HubProtocol val)
: Bool val
```
#### Parameters

*   that: [HubProtocol](wallaroo_labs-hub-HubProtocol) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: HubProtocol val)
: Bool val
```
#### Parameters

*   that: [HubProtocol](wallaroo_labs-hub-HubProtocol) val

#### Returns

* [Bool](builtin-Bool) val

---

