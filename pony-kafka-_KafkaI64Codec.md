# _KafkaI64Codec

```pony
primitive val _KafkaI64Codec
```

## Constructors

### create

```pony
new val create()
: _KafkaI64Codec val^
```

#### Returns

* [_KafkaI64Codec](pony-kafka-_KafkaI64Codec) val^

---

## Public Functions

### encode

```pony
fun box encode(
  wb: Writer ref,
  i: I64 val)
: None val
```
#### Parameters

*   wb: [Writer](.-custombuffered-Writer) ref
*   i: [I64](builtin-I64) val

#### Returns

* [None](builtin-None) val

---

### decode

```pony
fun box decode(
  logger: Logger[String val] val,
  rb: IsoReader ref,
  err_str: String val = seq)
: I64 val ?
```
#### Parameters

*   logger: [Logger](.-customlogger-Logger)\[[String](builtin-String) val\] val
*   rb: [IsoReader](.-custombuffered-IsoReader) ref
*   err_str: [String](builtin-String) val = seq

#### Returns

* [I64](builtin-I64) val ?

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
  that: _KafkaI64Codec val)
: Bool val
```
#### Parameters

*   that: [_KafkaI64Codec](pony-kafka-_KafkaI64Codec) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: _KafkaI64Codec val)
: Bool val
```
#### Parameters

*   that: [_KafkaI64Codec](pony-kafka-_KafkaI64Codec) val

#### Returns

* [Bool](builtin-Bool) val

---

