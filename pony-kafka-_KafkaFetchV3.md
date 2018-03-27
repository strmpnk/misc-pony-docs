# _KafkaFetchV3

```pony
primitive val _KafkaFetchV3 is
  _KafkaFetchApi val
```

#### Implements

* [_KafkaFetchApi](pony-kafka-_KafkaFetchApi) val

---

## Constructors

### create

```pony
new val create()
: _KafkaFetchV3 val^
```

#### Returns

* [_KafkaFetchV3](pony-kafka-_KafkaFetchV3) val^

---

## Public Functions

### version

```pony
fun box version()
: I16 val
```

#### Returns

* [I16](builtin-I16) val

---

### min_broker_version

```pony
fun box min_broker_version()
: String val
```

#### Returns

* [String](builtin-String) val

---

### encode_request

```pony
fun box encode_request(
  correlation_id: I32 val,
  conf: KafkaConfig val,
  topics_state: HashMap[String val, _KafkaTopicState ref, HashEq[String val] val] ref)
: (Array[(String val | Array[U8 val] val)] iso^ | None val)
```
#### Parameters

*   correlation_id: [I32](builtin-I32) val
*   conf: [KafkaConfig](pony-kafka-KafkaConfig) val
*   topics_state: [HashMap](collections-HashMap)\[[String](builtin-String) val, [_KafkaTopicState](pony-kafka-_KafkaTopicState) ref, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] ref

#### Returns

* ([Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] iso^ | [None](builtin-None) val)

---

### encode_request_body

```pony
fun box encode_request_body(
  wb: Writer ref,
  conf: KafkaConfig val,
  topics_state: HashMap[String val, _KafkaTopicState ref, HashEq[String val] val] ref)
: I32 val
```
#### Parameters

*   wb: [Writer](.-custombuffered-Writer) ref
*   conf: [KafkaConfig](pony-kafka-KafkaConfig) val
*   topics_state: [HashMap](collections-HashMap)\[[String](builtin-String) val, [_KafkaTopicState](pony-kafka-_KafkaTopicState) ref, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] ref

#### Returns

* [I32](builtin-I32) val

---

### decode_response

```pony
fun box decode_response(
  broker_conn: KafkaBrokerConnection tag,
  check_crc: Bool val,
  logger: Logger[String val] val,
  rb: IsoReader ref,
  topics_state: HashMap[String val, _KafkaTopicState ref, HashEq[String val] val] ref)
: (I32 val , HashMap[String val, _KafkaTopicFetchResult ref, HashEq[String val] val] ref) ?
```
#### Parameters

*   broker_conn: [KafkaBrokerConnection](pony-kafka-KafkaBrokerConnection) tag
*   check_crc: [Bool](builtin-Bool) val
*   logger: [Logger](.-customlogger-Logger)\[[String](builtin-String) val\] val
*   rb: [IsoReader](.-custombuffered-IsoReader) ref
*   topics_state: [HashMap](collections-HashMap)\[[String](builtin-String) val, [_KafkaTopicState](pony-kafka-_KafkaTopicState) ref, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] ref

#### Returns

* ([I32](builtin-I32) val , [HashMap](collections-HashMap)\[[String](builtin-String) val, [_KafkaTopicFetchResult](pony-kafka-_KafkaTopicFetchResult) ref, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] ref) ?

---

### api_key

```pony
fun box api_key()
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
  that: _KafkaFetchV3 val)
: Bool val
```
#### Parameters

*   that: [_KafkaFetchV3](pony-kafka-_KafkaFetchV3) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: _KafkaFetchV3 val)
: Bool val
```
#### Parameters

*   that: [_KafkaFetchV3](pony-kafka-_KafkaFetchV3) val

#### Returns

* [Bool](builtin-Bool) val

---

