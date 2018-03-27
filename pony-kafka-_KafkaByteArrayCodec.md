# _KafkaByteArrayCodec

```pony
primitive val _KafkaByteArrayCodec
```

## Constructors

### create

```pony
new val create()
: _KafkaByteArrayCodec val^
```

#### Returns

* [_KafkaByteArrayCodec](pony-kafka-_KafkaByteArrayCodec) val^

---

## Public Functions

### decode_default_none

```pony
fun box decode_default_none(
  logger: Logger[String val] val,
  rb: IsoReader ref,
  err_str: String val = seq)
: (Array[U8 val] iso^ | None val) ?
```
#### Parameters

*   logger: [Logger](.-customlogger-Logger)\[[String](builtin-String) val\] val
*   rb: [IsoReader](.-custombuffered-IsoReader) ref
*   err_str: [String](builtin-String) val = seq

#### Returns

* ([Array](builtin-Array)\[[U8](builtin-U8) val\] iso^ | [None](builtin-None) val) ?

---

### decode

```pony
fun box decode(
  logger: Logger[String val] val,
  rb: IsoReader ref,
  err_str: String val = seq)
: Array[U8 val] iso^ ?
```
#### Parameters

*   logger: [Logger](.-customlogger-Logger)\[[String](builtin-String) val\] val
*   rb: [IsoReader](.-custombuffered-IsoReader) ref
*   err_str: [String](builtin-String) val = seq

#### Returns

* [Array](builtin-Array)\[[U8](builtin-U8) val\] iso^ ?

---

### encoded_size

```pony
fun box encoded_size(
  num_bytes: USize val)
: I32 val
```
#### Parameters

*   num_bytes: [USize](builtin-USize) val

#### Returns

* [I32](builtin-I32) val

---

### encode

```pony
fun box encode(
  wb: Writer ref,
  bytes: (String val | Array[U8 val] val | Array[(String val | Array[U8 val] val)] val | 
    None val),
  num_bytes: USize val)
: None val
```
#### Parameters

*   wb: [Writer](.-custombuffered-Writer) ref
*   bytes: ([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val | [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val | 
    [None](builtin-None) val)
*   num_bytes: [USize](builtin-USize) val

#### Returns

* [None](builtin-None) val

---

### eq

```pony
fun box eq(
  that: _KafkaByteArrayCodec val)
: Bool val
```
#### Parameters

*   that: [_KafkaByteArrayCodec](pony-kafka-_KafkaByteArrayCodec) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: _KafkaByteArrayCodec val)
: Bool val
```
#### Parameters

*   that: [_KafkaByteArrayCodec](pony-kafka-_KafkaByteArrayCodec) val

#### Returns

* [Bool](builtin-Bool) val

---

