# KafkaEncoderWrapper

```pony
trait val KafkaEncoderWrapper
```

## Public Functions

### encode\[D: [Any](builtin-Any) val\]

```pony
fun box encode[D: Any val](
  d: D,
  wb: Writer ref)
: (Array[(String val | Array[U8 val] val)] val , (Array[(String val | Array[U8 val] val)] val | None val)) ?
```
#### Parameters

*   d: D
*   wb: [Writer](buffered-Writer) ref

#### Returns

* ([Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val , ([Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val | [None](builtin-None) val)) ?

---

