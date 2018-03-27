# _KafkaRequestHeader

```pony
primitive val _KafkaRequestHeader
```

## Constructors

### create

```pony
new val create()
: _KafkaRequestHeader val^
```

#### Returns

* [_KafkaRequestHeader](pony-kafka-_KafkaRequestHeader) val^

---

## Public Functions

### encode

```pony
fun box encode(
  wb: Writer ref,
  api_key: I16 val,
  api_version: I16 val,
  correlation_id: I32 val,
  conf: KafkaConfig val)
: None val
```
#### Parameters

*   wb: [Writer](.-custombuffered-Writer) ref
*   api_key: [I16](builtin-I16) val
*   api_version: [I16](builtin-I16) val
*   correlation_id: [I32](builtin-I32) val
*   conf: [KafkaConfig](pony-kafka-KafkaConfig) val

#### Returns

* [None](builtin-None) val

---

### decode

```pony
fun box decode(
  logger: Logger[String val] val,
  rb: IsoReader ref)
: (I16 val , I16 val , I32 val , 
    String val) ?
```
#### Parameters

*   logger: [Logger](.-customlogger-Logger)\[[String](builtin-String) val\] val
*   rb: [IsoReader](.-custombuffered-IsoReader) ref

#### Returns

* ([I16](builtin-I16) val , [I16](builtin-I16) val , [I32](builtin-I32) val , 
    [String](builtin-String) val) ?

---

### encoded_size

```pony
fun box encoded_size(
  client_name: String val)
: I32 val
```
#### Parameters

*   client_name: [String](builtin-String) val

#### Returns

* [I32](builtin-I32) val

---

### eq

```pony
fun box eq(
  that: _KafkaRequestHeader val)
: Bool val
```
#### Parameters

*   that: [_KafkaRequestHeader](pony-kafka-_KafkaRequestHeader) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: _KafkaRequestHeader val)
: Bool val
```
#### Parameters

*   that: [_KafkaRequestHeader](pony-kafka-_KafkaRequestHeader) val

#### Returns

* [Bool](builtin-Bool) val

---

