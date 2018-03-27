# KafkaErrorReport

```pony
class val KafkaErrorReport
```

## Constructors

### create

```pony
new val create(
  status': KafkaError val,
  topic': String val,
  partition': I32 val)
: KafkaErrorReport val^
```
#### Parameters

*   status': [KafkaError](pony-kafka-KafkaError) val
*   topic': [String](builtin-String) val
*   partition': [I32](builtin-I32) val

#### Returns

* [KafkaErrorReport](pony-kafka-KafkaErrorReport) val^

---

## Public fields

* let status: [KafkaError](pony-kafka-KafkaError) val

---

* let topic: [String](builtin-String) val

---

* let partition: [I32](builtin-I32) val

---

## Public Functions

### string

```pony
fun box string()
: String val
```

#### Returns

* [String](builtin-String) val

---

