# ClientErrorNoBrokerConnection

```pony
class val ClientErrorNoBrokerConnection is
  KafkaError val
```

#### Implements

* [KafkaError](pony-kafka-KafkaError) val

---

## Constructors

### create

```pony
new val create(
  broker_tag': KafkaBrokerConnection tag)
: ClientErrorNoBrokerConnection val^
```
#### Parameters

*   broker_tag': [KafkaBrokerConnection](pony-kafka-KafkaBrokerConnection) tag

#### Returns

* [ClientErrorNoBrokerConnection](pony-kafka-ClientErrorNoBrokerConnection) val^

---

## Public fields

* let broker_tag: [KafkaBrokerConnection](pony-kafka-KafkaBrokerConnection) tag

---

## Public Functions

### apply

```pony
fun box apply()
: I16 val
```

#### Returns

* [I16](builtin-I16) val

---

### string

```pony
fun box string()
: String val
```

#### Returns

* [String](builtin-String) val

---

### kafka_official

```pony
fun box kafka_official()
: Bool val
```

#### Returns

* [Bool](builtin-Bool) val

---

## Private Functions

### _retriable

```pony
fun box _retriable()
: Bool val
```

#### Returns

* [Bool](builtin-Bool) val

---

