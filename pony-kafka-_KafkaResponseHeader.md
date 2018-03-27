# _KafkaResponseHeader

```pony
primitive val _KafkaResponseHeader
```

## Constructors

### create

```pony
new val create()
: _KafkaResponseHeader val^
```

#### Returns

* [_KafkaResponseHeader](pony-kafka-_KafkaResponseHeader) val^

---

## Public Functions

### decode

```pony
fun box decode(
  logger: Logger[String val] val,
  rb: IsoReader ref)
: I32 val ?
```
#### Parameters

*   logger: [Logger](.-customlogger-Logger)\[[String](builtin-String) val\] val
*   rb: [IsoReader](.-custombuffered-IsoReader) ref

#### Returns

* [I32](builtin-I32) val ?

---

### eq

```pony
fun box eq(
  that: _KafkaResponseHeader val)
: Bool val
```
#### Parameters

*   that: [_KafkaResponseHeader](pony-kafka-_KafkaResponseHeader) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: _KafkaResponseHeader val)
: Bool val
```
#### Parameters

*   that: [_KafkaResponseHeader](pony-kafka-_KafkaResponseHeader) val

#### Returns

* [Bool](builtin-Bool) val

---

