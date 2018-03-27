# _RunOffsetsApiTest

Test kafka api


```pony
primitive val _RunOffsetsApiTest
```

## Constructors

### create

```pony
new val create()
: _RunOffsetsApiTest val^
```

#### Returns

* [_RunOffsetsApiTest](pony-kafka-_RunOffsetsApiTest) val^

---

## Public Functions

### apply

```pony
fun box apply(
  h: TestHelper val,
  api_to_use: _KafkaOffsetsApi val)
: None val ?
```
#### Parameters

*   h: [TestHelper](ponytest-TestHelper) val
*   api_to_use: [_KafkaOffsetsApi](pony-kafka-_KafkaOffsetsApi) val

#### Returns

* [None](builtin-None) val ?

---

### eq

```pony
fun box eq(
  that: _RunOffsetsApiTest val)
: Bool val
```
#### Parameters

*   that: [_RunOffsetsApiTest](pony-kafka-_RunOffsetsApiTest) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: _RunOffsetsApiTest val)
: Bool val
```
#### Parameters

*   that: [_RunOffsetsApiTest](pony-kafka-_RunOffsetsApiTest) val

#### Returns

* [Bool](builtin-Bool) val

---

