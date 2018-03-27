# SpikeConfig

```pony
class val SpikeConfig
```

## Constructors

### create

```pony
new val create(
  drop': Bool val = seq,
  prob': (F64 val | None val) = seq,
  margin': (USize val | None val) = seq,
  seed': (U64 val | None val) = seq)
: SpikeConfig val^ ?
```
#### Parameters

*   drop': [Bool](builtin-Bool) val = seq
*   prob': ([F64](builtin-F64) val | [None](builtin-None) val) = seq
*   margin': ([USize](builtin-USize) val | [None](builtin-None) val) = seq
*   seed': ([U64](builtin-U64) val | [None](builtin-None) val) = seq

#### Returns

* [SpikeConfig](wallaroo-ent-spike-SpikeConfig) val^ ?

---

## Public fields

* let drop: [Bool](builtin-Bool) val

---

* let seed: [U64](builtin-U64) val

---

* let prob: [F64](builtin-F64) val

---

* let margin: [USize](builtin-USize) val

---

