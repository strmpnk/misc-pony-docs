# _KafkaOffsetsApi

```pony
trait val _KafkaOffsetsApi is
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
  topics_state: HashMap[String val, _KafkaTopicState ref, HashEq[String val] val] box)
: Array[(String val | Array[U8 val] val)] iso^
```
#### Parameters

*   correlation_id: [I32](builtin-I32) val
*   conf: [KafkaConfig](pony-kafka-KafkaConfig) val
*   topics_state: [HashMap](collections-HashMap)\[[String](builtin-String) val, [_KafkaTopicState](pony-kafka-_KafkaTopicState) ref, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] box

#### Returns

* [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] iso^

---

### decode_request

```pony
fun box decode_request(
  logger: Logger[String val] val,
  rb: IsoReader ref)
: (I32 val , HashMap[String val, HashMap[I32 val, (I64 val , I32 val), HashEq[I32 val] val] val, HashEq[String val] val] val) ?
```
#### Parameters

*   logger: [Logger](.-customlogger-Logger)\[[String](builtin-String) val\] val
*   rb: [IsoReader](.-custombuffered-IsoReader) ref

#### Returns

* ([I32](builtin-I32) val , [HashMap](collections-HashMap)\[[String](builtin-String) val, [HashMap](collections-HashMap)\[[I32](builtin-I32) val, ([I64](builtin-I64) val , [I32](builtin-I32) val), [HashEq](collections-HashEq)\[[I32](builtin-I32) val\] val\] val, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val) ?

---

### decode_response

```pony
fun box decode_response(
  logger: Logger[String val] val,
  rb: IsoReader ref)
: Array[_KafkaTopicOffset ref] ref ?
```
#### Parameters

*   logger: [Logger](.-customlogger-Logger)\[[String](builtin-String) val\] val
*   rb: [IsoReader](.-custombuffered-IsoReader) ref

#### Returns

* [Array](builtin-Array)\[[_KafkaTopicOffset](pony-kafka-_KafkaTopicOffset) ref\] ref ?

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

