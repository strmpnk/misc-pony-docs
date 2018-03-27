# ProducerKafkaMessage

```pony
class ref ProducerKafkaMessage
```

## Constructors

### create

```pony
new ref create(
  created_by: KafkaProducer tag,
  opaque: Any tag,
  value: (String val | Array[U8 val] val | Array[(String val | Array[U8 val] val)] val),
  value_size: USize val,
  key: (String val | Array[U8 val] val | Array[(String val | Array[U8 val] val)] val | 
    None val) = seq,
  key_size: USize val = seq,
  timestamp: (I64 val | None val) = seq,
  timestamp_type: (KafkaTimestampNotAvailable val | KafkaCreateTimestamp val | KafkaLogAppendTimestamp val) = seq)
: ProducerKafkaMessage ref^
```
#### Parameters

*   created_by: [KafkaProducer](pony-kafka-KafkaProducer) tag
*   opaque: [Any](builtin-Any) tag
*   value: ([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val | [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val)
*   value_size: [USize](builtin-USize) val
*   key: ([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val | [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val | 
    [None](builtin-None) val) = seq
*   key_size: [USize](builtin-USize) val = seq
*   timestamp: ([I64](builtin-I64) val | [None](builtin-None) val) = seq
*   timestamp_type: ([KafkaTimestampNotAvailable](pony-kafka-KafkaTimestampNotAvailable) val | [KafkaCreateTimestamp](pony-kafka-KafkaCreateTimestamp) val | [KafkaLogAppendTimestamp](pony-kafka-KafkaLogAppendTimestamp) val) = seq

#### Returns

* [ProducerKafkaMessage](pony-kafka-ProducerKafkaMessage) ref^

---

## Public Functions

### get_opaque

```pony
fun box get_opaque()
: Any tag
```

#### Returns

* [Any](builtin-Any) tag

---

### get_value

```pony
fun box get_value()
: (String val | Array[U8 val] val | Array[(String val | Array[U8 val] val)] val)
```

#### Returns

* ([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val | [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val)

---

### get_value_size

```pony
fun box get_value_size()
: USize val
```

#### Returns

* [USize](builtin-USize) val

---

### get_key

```pony
fun box get_key()
: (String val | Array[U8 val] val | Array[(String val | Array[U8 val] val)] val | 
    None val)
```

#### Returns

* ([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val | [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val | 
    [None](builtin-None) val)

---

### get_key_size

```pony
fun box get_key_size()
: USize val
```

#### Returns

* [USize](builtin-USize) val

---

### get_timestamp

```pony
fun box get_timestamp()
: ((I64 val | None val) , (KafkaTimestampNotAvailable val | KafkaCreateTimestamp val | KafkaLogAppendTimestamp val))
```

#### Returns

* (([I64](builtin-I64) val | [None](builtin-None) val) , ([KafkaTimestampNotAvailable](pony-kafka-KafkaTimestampNotAvailable) val | [KafkaCreateTimestamp](pony-kafka-KafkaCreateTimestamp) val | [KafkaLogAppendTimestamp](pony-kafka-KafkaLogAppendTimestamp) val))

---

### string

```pony
fun box string()
: String val
```

#### Returns

* [String](builtin-String) val

---

## Private Functions

### _get_created_by

```pony
fun val _get_created_by()
: KafkaProducer tag
```

#### Returns

* [KafkaProducer](pony-kafka-KafkaProducer) tag

---

### _send_delivery_report

```pony
fun val _send_delivery_report(
  delivery_report: KafkaProducerDeliveryReport val)
: None val
```
#### Parameters

*   delivery_report: [KafkaProducerDeliveryReport](pony-kafka-KafkaProducerDeliveryReport) val

#### Returns

* [None](builtin-None) val

---

