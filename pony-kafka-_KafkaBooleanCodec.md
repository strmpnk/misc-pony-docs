# _KafkaBooleanCodec

```pony
primitive val _KafkaBooleanCodec
```

## Constructors

### create

```pony
new val create()
: _KafkaBooleanCodec val^
```

#### Returns

* [_KafkaBooleanCodec](pony-kafka-_KafkaBooleanCodec) val^

---

## Public Functions

### encode

```pony
fun box encode(
  wb: Writer ref,
  b: Bool val)
: None val
```
#### Parameters

*   wb: [Writer](.-custombuffered-Writer) ref
*   b: [Bool](builtin-Bool) val

#### Returns

* [None](builtin-None) val

---

### decode

```pony
fun box decode(
  logger: Logger[String val] val,
  rb: IsoReader ref,
  err_str: String val = seq)
: Bool val ?
```
#### Parameters

*   logger: [Logger](.-customlogger-Logger)\[[String](builtin-String) val\] val
*   rb: [IsoReader](.-custombuffered-IsoReader) ref
*   err_str: [String](builtin-String) val = seq

#### Returns

* [Bool](builtin-Bool) val ?

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
  that: _KafkaBooleanCodec val)
: Bool val
```
#### Parameters

*   that: [_KafkaBooleanCodec](pony-kafka-_KafkaBooleanCodec) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: _KafkaBooleanCodec val)
: Bool val
```
#### Parameters

*   that: [_KafkaBooleanCodec](pony-kafka-_KafkaBooleanCodec) val

#### Returns

* [Bool](builtin-Bool) val

---

