# KafkaSourceConfigCLIParser

```pony
primitive val KafkaSourceConfigCLIParser
```

## Constructors

### create

```pony
new val create()
: KafkaSourceConfigCLIParser val^
```

#### Returns

* [KafkaSourceConfigCLIParser](wallaroo-core-source-kafka_source-KafkaSourceConfigCLIParser) val^

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
  that: KafkaSourceConfigCLIParser val)
: Bool val
```
#### Parameters

*   that: [KafkaSourceConfigCLIParser](wallaroo-core-source-kafka_source-KafkaSourceConfigCLIParser) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: KafkaSourceConfigCLIParser val)
: Bool val
```
#### Parameters

*   that: [KafkaSourceConfigCLIParser](wallaroo-core-source-kafka_source-KafkaSourceConfigCLIParser) val

#### Returns

* [Bool](builtin-Bool) val

---

