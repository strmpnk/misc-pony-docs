# ErrorInvalidFetchSize

```pony
primitive val ErrorInvalidFetchSize is
  KafkaError val
```

#### Implements

* [KafkaError](pony-kafka-KafkaError) val

---

## Constructors

### create

```pony
new val create()
: ErrorInvalidFetchSize val^
```

#### Returns

* [ErrorInvalidFetchSize](pony-kafka-ErrorInvalidFetchSize) val^

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

### eq

```pony
fun box eq(
  that: ErrorInvalidFetchSize val)
: Bool val
```
#### Parameters

*   that: [ErrorInvalidFetchSize](pony-kafka-ErrorInvalidFetchSize) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: ErrorInvalidFetchSize val)
: Bool val
```
#### Parameters

*   that: [ErrorInvalidFetchSize](pony-kafka-ErrorInvalidFetchSize) val

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

