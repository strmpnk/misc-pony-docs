# FramedSourceHandler\[In: [Any](builtin-Any) val\]

```pony
interface ref FramedSourceHandler[In: Any val]
```

## Public Functions

### header_length

```pony
fun box header_length()
: USize val
```

#### Returns

* [USize](builtin-USize) val

---

### payload_length

```pony
fun box payload_length(
  data: Array[U8 val] iso)
: USize val ?
```
#### Parameters

*   data: [Array](builtin-Array)\[[U8](builtin-U8) val\] iso

#### Returns

* [USize](builtin-USize) val ?

---

### decode

```pony
fun box decode(
  data: Array[U8 val] val)
: In ?
```
#### Parameters

*   data: [Array](builtin-Array)\[[U8](builtin-U8) val\] val

#### Returns

* In ?

---

