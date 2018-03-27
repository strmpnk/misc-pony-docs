# TypedTCPEncoderWrapper\[In: [Any](builtin-Any) val\]

```pony
class val TypedTCPEncoderWrapper[In: Any val] is
  TCPEncoderWrapper val
```

#### Implements

* [TCPEncoderWrapper](wallaroo-core-sink-tcp_sink-TCPEncoderWrapper) val

---

## Constructors

### create

```pony
new val create(
  e: TCPSinkEncoder[In] val)
: TypedTCPEncoderWrapper[In] val^
```
#### Parameters

*   e: [TCPSinkEncoder](wallaroo-core-sink-tcp_sink-TCPSinkEncoder)\[In\] val

#### Returns

* [TypedTCPEncoderWrapper](wallaroo-core-sink-tcp_sink-TypedTCPEncoderWrapper)\[In\] val^

---

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

