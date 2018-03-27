# _KafkaFetchApi

```pony
trait val _KafkaFetchApi is
  _KafkaApi val
```

#### Implements

* [_KafkaApi](pony-kafka-_KafkaApi) val

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

### string

```pony
fun box string()
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

### apply

```pony
fun box apply()
: (I16 val , I16 val)
```

#### Returns

* ([I16](builtin-I16) val , [I16](builtin-I16) val)

---

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

