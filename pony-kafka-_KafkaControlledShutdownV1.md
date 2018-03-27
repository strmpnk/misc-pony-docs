# _KafkaControlledShutdownV1

```pony
primitive val _KafkaControlledShutdownV1 is
  _KafkaApi val
```

#### Implements

* [_KafkaApi](pony-kafka-_KafkaApi) val

---

## Constructors

### create

```pony
new val create()
: _KafkaControlledShutdownV1 val^
```

#### Returns

* [_KafkaControlledShutdownV1](pony-kafka-_KafkaControlledShutdownV1) val^

---

## Public Functions

### api_key

```pony
fun box api_key()
: I16 val
```

#### Returns

* [I16](builtin-I16) val

---

### version

```pony
fun box version()
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

### min_broker_version

```pony
fun box min_broker_version()
: String val
```

#### Returns

* [String](builtin-String) val

---

### apply

```pony
fun box apply()
: (I16 val , I16 val)
```

#### Returns

* ([I16](builtin-I16) val , [I16](builtin-I16) val)

---

### eq

```pony
fun box eq(
  that: _KafkaControlledShutdownV1 val)
: Bool val
```
#### Parameters

*   that: [_KafkaControlledShutdownV1](pony-kafka-_KafkaControlledShutdownV1) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: _KafkaControlledShutdownV1 val)
: Bool val
```
#### Parameters

*   that: [_KafkaControlledShutdownV1](pony-kafka-_KafkaControlledShutdownV1) val

#### Returns

* [Bool](builtin-Bool) val

---

