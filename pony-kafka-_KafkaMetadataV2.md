# _KafkaMetadataV2

```pony
primitive val _KafkaMetadataV2 is
  _KafkaMetadataApi val
```

#### Implements

* [_KafkaMetadataApi](pony-kafka-_KafkaMetadataApi) val

---

## Constructors

### create

```pony
new val create()
: _KafkaMetadataV2 val^
```

#### Returns

* [_KafkaMetadataV2](pony-kafka-_KafkaMetadataV2) val^

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
  conf: KafkaConfig val)
: Array[(String val | Array[U8 val] val)] iso^
```
#### Parameters

*   correlation_id: [I32](builtin-I32) val
*   conf: [KafkaConfig](pony-kafka-KafkaConfig) val

#### Returns

* [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] iso^

---

### decode_response

```pony
fun box decode_response(
  logger: Logger[String val] val,
  rb: IsoReader ref)
: _KafkaMetadata val ?
```
#### Parameters

*   logger: [Logger](.-customlogger-Logger)\[[String](builtin-String) val\] val
*   rb: [IsoReader](.-custombuffered-IsoReader) ref

#### Returns

* [_KafkaMetadata](pony-kafka-_KafkaMetadata) val ?

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
  that: _KafkaMetadataV2 val)
: Bool val
```
#### Parameters

*   that: [_KafkaMetadataV2](pony-kafka-_KafkaMetadataV2) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: _KafkaMetadataV2 val)
: Bool val
```
#### Parameters

*   that: [_KafkaMetadataV2](pony-kafka-_KafkaMetadataV2) val

#### Returns

* [Bool](builtin-Bool) val

---

