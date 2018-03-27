# _KafkaStringCodec

```pony
primitive val _KafkaStringCodec
```

## Constructors

### create

```pony
new val create()
: _KafkaStringCodec val^
```

#### Returns

* [_KafkaStringCodec](pony-kafka-_KafkaStringCodec) val^

---

## Public Functions

### encode

```pony
fun box encode(
  wb: Writer ref,
  str: String val)
: None val
```
#### Parameters

*   wb: [Writer](.-custombuffered-Writer) ref
*   str: [String](builtin-String) val

#### Returns

* [None](builtin-None) val

---

### decode

```pony
fun box decode(
  logger: Logger[String val] val,
  rb: IsoReader ref,
  err_str: String val = seq)
: String iso^ ?
```
#### Parameters

*   logger: [Logger](.-customlogger-Logger)\[[String](builtin-String) val\] val
*   rb: [IsoReader](.-custombuffered-IsoReader) ref
*   err_str: [String](builtin-String) val = seq

#### Returns

* [String](builtin-String) iso^ ?

---

### encoded_size

```pony
fun box encoded_size(
  str: String val)
: I32 val
```
#### Parameters

*   str: [String](builtin-String) val

#### Returns

* [I32](builtin-I32) val

---

### eq

```pony
fun box eq(
  that: _KafkaStringCodec val)
: Bool val
```
#### Parameters

*   that: [_KafkaStringCodec](pony-kafka-_KafkaStringCodec) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: _KafkaStringCodec val)
: Bool val
```
#### Parameters

*   that: [_KafkaStringCodec](pony-kafka-_KafkaStringCodec) val

#### Returns

* [Bool](builtin-Bool) val

---

