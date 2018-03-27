# KafkaProducerMessageHandler

```pony
trait ref KafkaProducerMessageHandler
```

## Public Functions

### apply

```pony
fun ref apply(
  key: (String val | Array[U8 val] val | Array[(String val | Array[U8 val] val)] val | 
    None val),
  key_size: USize val,
  num_partitions: I32 val)
: (I32 val | None val)
```
#### Parameters

*   key: ([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val | [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val | 
    [None](builtin-None) val)
*   key_size: [USize](builtin-USize) val
*   num_partitions: [I32](builtin-I32) val

#### Returns

* ([I32](builtin-I32) val | [None](builtin-None) val)

---

### clone

```pony
fun box clone()
: KafkaProducerMessageHandler iso^
```

#### Returns

* [KafkaProducerMessageHandler](pony-kafka-KafkaProducerMessageHandler) iso^

---

