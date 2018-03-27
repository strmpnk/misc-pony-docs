# KafkaSinkConfigCLIParser

```pony
primitive val KafkaSinkConfigCLIParser
```

## Constructors

### create

```pony
new val create()
: KafkaSinkConfigCLIParser val^
```

#### Returns

* [KafkaSinkConfigCLIParser](wallaroo-core-sink-kafka_sink-KafkaSinkConfigCLIParser) val^

---

## Public Functions

### apply

```pony
fun box apply(
  out: OutStream tag,
  prefix: String val = seq)
: KafkaConfigCLIParser ref
```
#### Parameters

*   out: [OutStream](builtin-OutStream) tag
*   prefix: [String](builtin-String) val = seq

#### Returns

* [KafkaConfigCLIParser](pony-kafka-KafkaConfigCLIParser) ref

---

### eq

```pony
fun box eq(
  that: KafkaSinkConfigCLIParser val)
: Bool val
```
#### Parameters

*   that: [KafkaSinkConfigCLIParser](wallaroo-core-sink-kafka_sink-KafkaSinkConfigCLIParser) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: KafkaSinkConfigCLIParser val)
: Bool val
```
#### Parameters

*   that: [KafkaSinkConfigCLIParser](wallaroo-core-sink-kafka_sink-KafkaSinkConfigCLIParser) val

#### Returns

* [Bool](builtin-Bool) val

---

