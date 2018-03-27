# HubMetricsMsg

```pony
class val HubMetricsMsg is
  HubProtocolMsg val
```

#### Implements

* [HubProtocolMsg](wallaroo_labs-hub-HubProtocolMsg) val

---

## Constructors

### create

```pony
new val create(
  data: Array[U8 val] val)
: HubMetricsMsg val^ ?
```
#### Parameters

*   data: [Array](builtin-Array)\[[U8](builtin-U8) val\] val

#### Returns

* [HubMetricsMsg](wallaroo_labs-hub-HubMetricsMsg) val^ ?

---

## Public fields

* var name: [String](builtin-String) val

---

* var category: [String](builtin-String) val

---

* var pipeline_name: [String](builtin-String) val

---

* var worker_name: [String](builtin-String) val

---

* var id: [U16](builtin-U16) val

---

* var period_ends_at: [U64](builtin-U64) val

---

* var period: [U64](builtin-U64) val

---

* var histogram_min: [U64](builtin-U64) val

---

* var histogram_max: [U64](builtin-U64) val

---

* var histogram: [Array](builtin-Array)\[[U64](builtin-U64) val\] ref

---

