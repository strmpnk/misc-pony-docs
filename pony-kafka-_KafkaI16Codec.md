# _KafkaI16Codec

```pony
primitive val _KafkaI16Codec
```

## Constructors

### create

```pony
new val create()
: _KafkaI16Codec val^
```

#### Returns

* [_KafkaI16Codec](pony-kafka-_KafkaI16Codec) val^

---

## Public Functions

### encode

```pony
fun box encode(
  wb: Writer ref,
  i: I16 val)
: None val
```
#### Parameters

*   wb: [Writer](.-custombuffered-Writer) ref
*   i: [I16](builtin-I16) val

#### Returns

* [None](builtin-None) val

---

### decode

```pony
fun box decode(
  logger: Logger[String val] val,
  rb: IsoReader ref,
  err_str: String val = seq)
: I16 val ?
```
#### Parameters

*   logger: [Logger](.-customlogger-Logger)\[[String](builtin-String) val\] val
*   rb: [IsoReader](.-custombuffered-IsoReader) ref
*   err_str: [String](builtin-String) val = seq

#### Returns

* [I16](builtin-I16) val ?

---

### encoded_size

```pony
fun box encoded_size()
: I32 val
```

#### Returns

* [I32](builtin-I32) val

---

### eq

```pony
fun box eq(
  that: _KafkaI16Codec val)
: Bool val
```
#### Parameters

*   that: [_KafkaI16Codec](pony-kafka-_KafkaI16Codec) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: _KafkaI16Codec val)
: Bool val
```
#### Parameters

*   that: [_KafkaI16Codec](pony-kafka-_KafkaI16Codec) val

#### Returns

* [Bool](builtin-Bool) val

---

