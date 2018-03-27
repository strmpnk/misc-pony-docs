# TypedKafkaEncoderWrapper\[In: [Any](builtin-Any) val\]

```pony
class val TypedKafkaEncoderWrapper[In: Any val] is
  KafkaEncoderWrapper val
```

#### Implements

* [KafkaEncoderWrapper](wallaroo-core-sink-kafka_sink-KafkaEncoderWrapper) val

---

## Constructors

### create

```pony
new val create(
  e: KafkaSinkEncoder[In] val)
: TypedKafkaEncoderWrapper[In] val^
```
#### Parameters

*   e: [KafkaSinkEncoder](wallaroo-core-sink-kafka_sink-KafkaSinkEncoder)\[In\] val

#### Returns

* [TypedKafkaEncoderWrapper](wallaroo-core-sink-kafka_sink-TypedKafkaEncoderWrapper)\[In\] val^

---

## Public Functions

### encode\[D: [Any](builtin-Any) val\]

```pony
fun box encode[D: Any val](
  data: D,
  wb: Writer ref)
: (Array[(String val | Array[U8 val] val)] val , (Array[(String val | Array[U8 val] val)] val | None val)) ?
```
#### Parameters

*   data: D
*   wb: [Writer](buffered-Writer) ref

#### Returns

* ([Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val , ([Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val | [None](builtin-None) val)) ?

---

