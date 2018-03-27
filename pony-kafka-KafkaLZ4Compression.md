# KafkaLZ4Compression

```pony
primitive val KafkaLZ4Compression
```

## Constructors

### create

```pony
new val create()
: KafkaLZ4Compression val^
```

#### Returns

* [KafkaLZ4Compression](pony-kafka-KafkaLZ4Compression) val^

---

## Public Functions

### break_frame_header

```pony
fun box break_frame_header(
  logger: Logger[String val] val,
  data: Array[U8 val] ref)
: None val ?
```
#### Parameters

*   logger: [Logger](.-customlogger-Logger)\[[String](builtin-String) val\] val
*   data: [Array](builtin-Array)\[[U8](builtin-U8) val\] ref

#### Returns

* [None](builtin-None) val ?

---

### unbreak_frame_header

```pony
fun box unbreak_frame_header(
  logger: Logger[String val] val,
  data: Array[U8 val] iso)
: Array[U8 val] iso^ ?
```
#### Parameters

*   logger: [Logger](.-customlogger-Logger)\[[String](builtin-String) val\] val
*   data: [Array](builtin-Array)\[[U8](builtin-U8) val\] iso

#### Returns

* [Array](builtin-Array)\[[U8](builtin-U8) val\] iso^ ?

---

### eq

```pony
fun box eq(
  that: KafkaLZ4Compression val)
: Bool val
```
#### Parameters

*   that: [KafkaLZ4Compression](pony-kafka-KafkaLZ4Compression) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: KafkaLZ4Compression val)
: Bool val
```
#### Parameters

*   that: [KafkaLZ4Compression](pony-kafka-KafkaLZ4Compression) val

#### Returns

* [Bool](builtin-Bool) val

---

