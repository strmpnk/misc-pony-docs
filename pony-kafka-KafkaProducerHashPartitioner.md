# KafkaProducerHashPartitioner

```pony
class ref KafkaProducerHashPartitioner is
  KafkaProducerMessageHandler ref
```

#### Implements

* [KafkaProducerMessageHandler](pony-kafka-KafkaProducerMessageHandler) ref

---

## Constructors

### create

```pony
new ref create()
: KafkaProducerHashPartitioner ref^
```

#### Returns

* [KafkaProducerHashPartitioner](pony-kafka-KafkaProducerHashPartitioner) ref^

---

## Public Functions

### clone

```pony
fun box clone()
: KafkaProducerMessageHandler iso^
```

#### Returns

* [KafkaProducerMessageHandler](pony-kafka-KafkaProducerMessageHandler) iso^

---

### apply

```pony
fun ref apply(
  key: (String val | Array[U8 val] val | Array[(String val | Array[U8 val] val)] val | 
    None val),
  key_size: USize val,
  num_partitions: I32 val)
: (None val | I32 val)
```
#### Parameters

*   key: ([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val | [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val | 
    [None](builtin-None) val)
*   key_size: [USize](builtin-USize) val
*   num_partitions: [I32](builtin-I32) val

#### Returns

* ([None](builtin-None) val | [I32](builtin-I32) val)

---

