# _Simple

```pony
class ref _Simple
```

## Constructors

### create

```pony
new iso create()
: _Simple iso^
```

#### Returns

* [_Simple](serialise-_Simple) iso^

---

## Public fields

* var words1: [_MachineWords](serialise-_MachineWords) ref

---

* embed words2: [_MachineWords](serialise-_MachineWords) ref

---

* var words3: [_StructWords](serialise-_StructWords) ref

---

* embed words4: [_StructWords](serialise-_StructWords) ref

---

* var words5: ([Any](builtin-Any) ref | [None](builtin-None) val)

---

* var words6: ([Any](builtin-Any) ref | [None](builtin-None) val)

---

* var string: [String](builtin-String) val

---

* var none: [None](builtin-None) val

---

* var tuple: ([U64](builtin-U64) val , [String](builtin-String) val)

---

* var tuple2: (([U64](builtin-U64) val , [String](builtin-String) val) | [None](builtin-None) val)

---

* var a_tag: [_MachineWords](serialise-_MachineWords) tag

---

* var a_ref: [_MachineWords](serialise-_MachineWords) ref

---

## Public Functions

### eq

```pony
fun box eq(
  that: _Simple ref)
: Bool val
```
#### Parameters

*   that: [_Simple](serialise-_Simple) ref

#### Returns

* [Bool](builtin-Bool) val

---

