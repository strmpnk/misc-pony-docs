# KafkaConfigFactory

```pony
primitive val KafkaConfigFactory
```

## Constructors

### create

```pony
new val create()
: KafkaConfigFactory val^
```

#### Returns

* [KafkaConfigFactory](pony-kafka-KafkaConfigFactory) val^

---

## Public Functions

### apply

```pony
fun box apply(
  kco: KafkaConfigOptions val,
  out: OutStream tag)
: (KafkaConfig iso^ | KafkaConfigError val)
```
#### Parameters

*   kco: [KafkaConfigOptions](pony-kafka-KafkaConfigOptions) val
*   out: [OutStream](builtin-OutStream) tag

#### Returns

* ([KafkaConfig](pony-kafka-KafkaConfig) iso^ | [KafkaConfigError](pony-kafka-KafkaConfigError) val)

---

### eq

```pony
fun box eq(
  that: KafkaConfigFactory val)
: Bool val
```
#### Parameters

*   that: [KafkaConfigFactory](pony-kafka-KafkaConfigFactory) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: KafkaConfigFactory val)
: Bool val
```
#### Parameters

*   that: [KafkaConfigFactory](pony-kafka-KafkaConfigFactory) val

#### Returns

* [Bool](builtin-Bool) val

---

## Private Functions

### _parse_offset

```pony
fun box _parse_offset(
  offset: String val,
  offset_default: (KafkaOffsetBeginning val | KafkaOffsetEnd val | I32 val | 
    None val))
: (KafkaOffsetBeginning val | KafkaOffsetEnd val | I32 val) ?
```
#### Parameters

*   offset: [String](builtin-String) val
*   offset_default: ([KafkaOffsetBeginning](pony-kafka-KafkaOffsetBeginning) val | [KafkaOffsetEnd](pony-kafka-KafkaOffsetEnd) val | [I32](builtin-I32) val | 
    [None](builtin-None) val)

#### Returns

* ([KafkaOffsetBeginning](pony-kafka-KafkaOffsetBeginning) val | [KafkaOffsetEnd](pony-kafka-KafkaOffsetEnd) val | [I32](builtin-I32) val) ?

---

### _parse_partitions

```pony
fun box _parse_partitions(
  partitions: String val,
  offset_default: (KafkaOffsetBeginning val | KafkaOffsetEnd val | I32 val))
: Array[(I32 val , (KafkaOffsetBeginning val | KafkaOffsetEnd val | I32 val))] val ?
```
#### Parameters

*   partitions: [String](builtin-String) val
*   offset_default: ([KafkaOffsetBeginning](pony-kafka-KafkaOffsetBeginning) val | [KafkaOffsetEnd](pony-kafka-KafkaOffsetEnd) val | [I32](builtin-I32) val)

#### Returns

* [Array](builtin-Array)\[([I32](builtin-I32) val , ([KafkaOffsetBeginning](pony-kafka-KafkaOffsetBeginning) val | [KafkaOffsetEnd](pony-kafka-KafkaOffsetEnd) val | [I32](builtin-I32) val))\] val ?

---

