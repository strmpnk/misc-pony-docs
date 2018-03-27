# KafkaTopicPartition

```pony
class val KafkaTopicPartition is
  Equatable[KafkaTopicPartition box] ref
```

#### Implements

* [Equatable](builtin-Equatable)\[[KafkaTopicPartition](pony-kafka-KafkaTopicPartition) box\] ref

---

## Constructors

### create

```pony
new val create(
  topic': String val,
  partition_id': I32 val)
: KafkaTopicPartition val^
```
#### Parameters

*   topic': [String](builtin-String) val
*   partition_id': [I32](builtin-I32) val

#### Returns

* [KafkaTopicPartition](pony-kafka-KafkaTopicPartition) val^

---

## Public fields

* let topic: [String](builtin-String) val

---

* let partition_id: [I32](builtin-I32) val

---

## Public Functions

### hash

```pony
fun box hash()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### eq

```pony
fun box eq(
  that: KafkaTopicPartition box)
: Bool val
```
#### Parameters

*   that: [KafkaTopicPartition](pony-kafka-KafkaTopicPartition) box

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: KafkaTopicPartition box)
: Bool val
```
#### Parameters

*   that: [KafkaTopicPartition](pony-kafka-KafkaTopicPartition) box

#### Returns

* [Bool](builtin-Bool) val

---

