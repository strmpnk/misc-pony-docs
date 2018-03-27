# KafkaProducerDeliveryReport

```pony
class val KafkaProducerDeliveryReport
```

## Constructors

### create

```pony
new val create(
  status': KafkaError val,
  topic': String val,
  partition': I32 val,
  first_offset_assigned': I64 val,
  timestamp': (I64 val | None val),
  opaque': Any tag)
: KafkaProducerDeliveryReport val^
```
#### Parameters

*   status': [KafkaError](pony-kafka-KafkaError) val
*   topic': [String](builtin-String) val
*   partition': [I32](builtin-I32) val
*   first_offset_assigned': [I64](builtin-I64) val
*   timestamp': ([I64](builtin-I64) val | [None](builtin-None) val)
*   opaque': [Any](builtin-Any) tag

#### Returns

* [KafkaProducerDeliveryReport](pony-kafka-KafkaProducerDeliveryReport) val^

---

## Public fields

* let status: [KafkaError](pony-kafka-KafkaError) val

---

* let topic: [String](builtin-String) val

---

* let partition: [I32](builtin-I32) val

---

* let first_offset_assigned: [I64](builtin-I64) val

---

* let timestamp: ([I64](builtin-I64) val | [None](builtin-None) val)

---

* let opaque: [Any](builtin-Any) tag

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

