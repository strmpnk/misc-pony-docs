# _RunProduceApiTest

Test kafka api


```pony
primitive val _RunProduceApiTest
```

## Constructors

### create

```pony
new val create()
: _RunProduceApiTest val^
```

#### Returns

* [_RunProduceApiTest](pony-kafka-_RunProduceApiTest) val^

---

## Public Functions

### apply

```pony
fun box apply(
  h: TestHelper val,
  compression: (KafkaNoTopicCompression val | KafkaGzipTopicCompression val | KafkaSnappyTopicCompression val | 
    KafkaLZ4TopicCompression val),
  api_to_use: _KafkaProduceApi val)
: None val ?
```
#### Parameters

*   h: [TestHelper](ponytest-TestHelper) val
*   compression: ([KafkaNoTopicCompression](pony-kafka-KafkaNoTopicCompression) val | [KafkaGzipTopicCompression](pony-kafka-KafkaGzipTopicCompression) val | [KafkaSnappyTopicCompression](pony-kafka-KafkaSnappyTopicCompression) val | 
    [KafkaLZ4TopicCompression](pony-kafka-KafkaLZ4TopicCompression) val)
*   api_to_use: [_KafkaProduceApi](pony-kafka-_KafkaProduceApi) val

#### Returns

* [None](builtin-None) val ?

---

### eq

```pony
fun box eq(
  that: _RunProduceApiTest val)
: Bool val
```
#### Parameters

*   that: [_RunProduceApiTest](pony-kafka-_RunProduceApiTest) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: _RunProduceApiTest val)
: Bool val
```
#### Parameters

*   that: [_RunProduceApiTest](pony-kafka-_RunProduceApiTest) val

#### Returns

* [Bool](builtin-Bool) val

---

