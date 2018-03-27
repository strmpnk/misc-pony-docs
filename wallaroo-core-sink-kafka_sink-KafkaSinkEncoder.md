# KafkaSinkEncoder\[In: [Any](builtin-Any) val\]

```pony
interface val KafkaSinkEncoder[In: Any val]
```

## Public Functions

### apply

```pony
fun box apply(
  input: In,
  wb: Writer ref)
: (Array[(String val | Array[U8 val] val)] val , (Array[(String val | Array[U8 val] val)] val | None val))
```
#### Parameters

*   input: In
*   wb: [Writer](buffered-Writer) ref

#### Returns

* ([Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val , ([Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val | [None](builtin-None) val))

---

