# MapKafkaError

```pony
primitive val MapKafkaError
```

## Constructors

### create

```pony
new val create()
: MapKafkaError val^
```

#### Returns

* [MapKafkaError](pony-kafka-MapKafkaError) val^

---

## Public Functions

### apply

```pony
fun box apply(
  logger: Logger[String val] val,
  error_code: I16 val)
: KafkaError val
```
#### Parameters

*   logger: [Logger](.-customlogger-Logger)\[[String](builtin-String) val\] val
*   error_code: [I16](builtin-I16) val

#### Returns

* [KafkaError](pony-kafka-KafkaError) val

---

### eq

```pony
fun box eq(
  that: MapKafkaError val)
: Bool val
```
#### Parameters

*   that: [MapKafkaError](pony-kafka-MapKafkaError) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: MapKafkaError val)
: Bool val
```
#### Parameters

*   that: [MapKafkaError](pony-kafka-MapKafkaError) val

#### Returns

* [Bool](builtin-Bool) val

---

