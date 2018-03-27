# _KafkaI32Codec

```pony
primitive val _KafkaI32Codec
```

## Constructors

### create

```pony
new val create()
: _KafkaI32Codec val^
```

#### Returns

* [_KafkaI32Codec](pony-kafka-_KafkaI32Codec) val^

---

## Public Functions

### encode

```pony
fun box encode(
  wb: Writer ref,
  i: I32 val)
: None val
```
#### Parameters

*   wb: [Writer](.-custombuffered-Writer) ref
*   i: [I32](builtin-I32) val

#### Returns

* [None](builtin-None) val

---

### decode

```pony
fun box decode(
  logger: Logger[String val] val,
  rb: IsoReader ref,
  err_str: String val = seq)
: I32 val ?
```
#### Parameters

*   logger: [Logger](.-customlogger-Logger)\[[String](builtin-String) val\] val
*   rb: [IsoReader](.-custombuffered-IsoReader) ref
*   err_str: [String](builtin-String) val = seq

#### Returns

* [I32](builtin-I32) val ?

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
  that: _KafkaI32Codec val)
: Bool val
```
#### Parameters

*   that: [_KafkaI32Codec](pony-kafka-_KafkaI32Codec) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: _KafkaI32Codec val)
: Bool val
```
#### Parameters

*   that: [_KafkaI32Codec](pony-kafka-_KafkaI32Codec) val

#### Returns

* [Bool](builtin-Bool) val

---

