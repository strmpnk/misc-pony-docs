# KafkaConfigCLIParser

```pony
class ref KafkaConfigCLIParser
```

## Constructors

### create

```pony
new ref create(
  out: OutStream tag,
  client_mode: (KafkaConsumeOnly val | KafkaProduceOnly val | KafkaProduceAndConsume val) = seq,
  client_name: String val = seq,
  prefix: (String val | None val) = seq)
: KafkaConfigCLIParser ref^
```
#### Parameters

*   out: [OutStream](builtin-OutStream) tag
*   client_mode: ([KafkaConsumeOnly](pony-kafka-KafkaConsumeOnly) val | [KafkaProduceOnly](pony-kafka-KafkaProduceOnly) val | [KafkaProduceAndConsume](pony-kafka-KafkaProduceAndConsume) val) = seq
*   client_name: [String](builtin-String) val = seq
*   prefix: ([String](builtin-String) val | [None](builtin-None) val) = seq

#### Returns

* [KafkaConfigCLIParser](pony-kafka-KafkaConfigCLIParser) ref^

---

## Public Functions

### opts

```pony
fun box opts()
: Array[(String val , (None val | String val) , (None val | StringArgument val | I64Argument val | F64Argument val) , (Required val | Optional val) , String val)] ref
```

#### Returns

* [Array](builtin-Array)\[([String](builtin-String) val , ([None](builtin-None) val | [String](builtin-String) val) , ([None](builtin-None) val | [StringArgument](options-StringArgument) val | [I64Argument](options-I64Argument) val | [F64Argument](options-F64Argument) val) , ([Required](options-Required) val | [Optional](options-Optional) val) , [String](builtin-String) val)\] ref

---

### print_usage

```pony
fun box print_usage()
: None val
```

#### Returns

* [None](builtin-None) val

---

### parse

```pony
fun box parse(
  args: Array[String val] val)
: KafkaConfig iso^ ?
```
#### Parameters

*   args: [Array](builtin-Array)\[[String](builtin-String) val\] val

#### Returns

* [KafkaConfig](pony-kafka-KafkaConfig) iso^ ?

---

### parse_options

```pony
fun box parse_options(
  args: Array[String val] val)
: KafkaConfigOptions iso^ ?
```
#### Parameters

*   args: [Array](builtin-Array)\[[String](builtin-String) val\] val

#### Returns

* [KafkaConfigOptions](pony-kafka-KafkaConfigOptions) iso^ ?

---

## Private Functions

### _prefix

```pony
fun tag _prefix(
  prefix: (String val | None val) = seq)
: String val
```
#### Parameters

*   prefix: ([String](builtin-String) val | [None](builtin-None) val) = seq

#### Returns

* [String](builtin-String) val

---

### _clean_string

```pony
fun tag _clean_string(
  s: String val)
: String val
```
#### Parameters

*   s: [String](builtin-String) val

#### Returns

* [String](builtin-String) val

---

### _brokers_from_input_string

```pony
fun box _brokers_from_input_string(
  inputs: String val)
: Array[(String val , I32 val)] val ?
```
#### Parameters

*   inputs: [String](builtin-String) val

#### Returns

* [Array](builtin-Array)\[([String](builtin-String) val , [I32](builtin-I32) val)\] val ?

---

### _topics_from_input_string

```pony
fun box _topics_from_input_string(
  inputs: String val)
: Array[String val] val
```
#### Parameters

*   inputs: [String](builtin-String) val

#### Returns

* [Array](builtin-Array)\[[String](builtin-String) val\] val

---

