# TCPEncoderWrapper

```pony
trait val TCPEncoderWrapper
```

## Public Functions

### encode\[D: [Any](builtin-Any) val\]

```pony
fun box encode[D: Any val](
  d: D,
  wb: Writer ref)
: Array[(String val | Array[U8 val] val)] val ?
```
#### Parameters

*   d: D
*   wb: [Writer](buffered-Writer) ref

#### Returns

* [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val ?

---

