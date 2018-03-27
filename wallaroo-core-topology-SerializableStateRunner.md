# SerializableStateRunner

```pony
interface ref SerializableStateRunner
```

## Public Functions

### serialize_state

```pony
fun ref serialize_state()
: (String val | Array[U8 val] val)
```

#### Returns

* ([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)

---

### replace_serialized_state

```pony
fun ref replace_serialized_state(
  s: (String val | Array[U8 val] val))
: None val
```
#### Parameters

*   s: ([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)

#### Returns

* [None](builtin-None) val

---

