# KafkaProducerMapping

```pony
class ref KafkaProducerMapping
```

## Constructors

### create

```pony
new ref create(
  kc': KafkaClient tag,
  conf': KafkaConfig val,
  topic_mapping': HashMap[String val, HashMap[I32 val, I32 val, HashEq[I32 val] val] ref, HashEq[String val] val] val,
  brokers': HashMap[I32 val, (_KafkaBroker val , KafkaBrokerConnection tag), HashEq[I32 val] val] val,
  producer: KafkaProducer tag)
: KafkaProducerMapping ref^
```
#### Parameters

*   kc': [KafkaClient](pony-kafka-KafkaClient) tag
*   conf': [KafkaConfig](pony-kafka-KafkaConfig) val
*   topic_mapping': [HashMap](collections-HashMap)\[[String](builtin-String) val, [HashMap](collections-HashMap)\[[I32](builtin-I32) val, [I32](builtin-I32) val, [HashEq](collections-HashEq)\[[I32](builtin-I32) val\] val\] ref, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val
*   brokers': [HashMap](collections-HashMap)\[[I32](builtin-I32) val, ([_KafkaBroker](pony-kafka-_KafkaBroker) val , [KafkaBrokerConnection](pony-kafka-KafkaBrokerConnection) tag), [HashEq](collections-HashEq)\[[I32](builtin-I32) val\] val\] val
*   producer: [KafkaProducer](pony-kafka-KafkaProducer) tag

#### Returns

* [KafkaProducerMapping](pony-kafka-KafkaProducerMapping) ref^

---

## Public fields

* let kc: [KafkaClient](pony-kafka-KafkaClient) tag

---

* let conf: [KafkaConfig](pony-kafka-KafkaConfig) val

---

* var topic_mapping: [HashMap](collections-HashMap)\[[String](builtin-String) val, [HashMap](collections-HashMap)\[[I32](builtin-I32) val, [I32](builtin-I32) val, [HashEq](collections-HashEq)\[[I32](builtin-I32) val\] val\] ref, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val

---

* var brokers: [HashMap](collections-HashMap)\[[I32](builtin-I32) val, ([_KafkaBroker](pony-kafka-_KafkaBroker) val , [KafkaBrokerConnection](pony-kafka-KafkaBrokerConnection) tag), [HashEq](collections-HashEq)\[[I32](builtin-I32) val\] val\] val

---

* let topic_partitioners: [HashMap](collections-HashMap)\[[String](builtin-String) val, [KafkaProducerMessageHandler](pony-kafka-KafkaProducerMessageHandler) ref, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] ref

---

## Public Functions

### update_brokers_and_topic_mapping

```pony
fun ref update_brokers_and_topic_mapping(
  brokers': HashMap[I32 val, (_KafkaBroker val , KafkaBrokerConnection tag), HashEq[I32 val] val] val,
  topic_mapping': HashMap[String val, HashMap[I32 val, I32 val, HashEq[I32 val] val] ref, HashEq[String val] val] val)
: None val
```
#### Parameters

*   brokers': [HashMap](collections-HashMap)\[[I32](builtin-I32) val, ([_KafkaBroker](pony-kafka-_KafkaBroker) val , [KafkaBrokerConnection](pony-kafka-KafkaBrokerConnection) tag), [HashEq](collections-HashEq)\[[I32](builtin-I32) val\] val\] val
*   topic_mapping': [HashMap](collections-HashMap)\[[String](builtin-String) val, [HashMap](collections-HashMap)\[[I32](builtin-I32) val, [I32](builtin-I32) val, [HashEq](collections-HashEq)\[[I32](builtin-I32) val\] val\] ref, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val

#### Returns

* [None](builtin-None) val

---

### update_topic_mapping

```pony
fun ref update_topic_mapping(
  topic_mapping': HashMap[String val, HashMap[I32 val, I32 val, HashEq[I32 val] val] ref, HashEq[String val] val] val)
: None val
```
#### Parameters

*   topic_mapping': [HashMap](collections-HashMap)\[[String](builtin-String) val, [HashMap](collections-HashMap)\[[I32](builtin-I32) val, [I32](builtin-I32) val, [HashEq](collections-HashEq)\[[I32](builtin-I32) val\] val\] ref, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val

#### Returns

* [None](builtin-None) val

---

### send_topic_messages

```pony
fun ref send_topic_messages(
  topic: String val,
  msgs: Array[(Any tag , (String val | Array[U8 val] val | Array[(String val | Array[U8 val] val)] val) , (None val | String val | Array[U8 val] val | Array[(String val | Array[U8 val] val)] val))] ref)
: (None val | Array[(KafkaError val , I32 val , Any tag)] ref)
```
#### Parameters

*   topic: [String](builtin-String) val
*   msgs: [Array](builtin-Array)\[([Any](builtin-Any) tag , ([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val | [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val) , ([None](builtin-None) val | [String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val | [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val))\] ref

#### Returns

* ([None](builtin-None) val | [Array](builtin-Array)\[([KafkaError](pony-kafka-KafkaError) val , [I32](builtin-I32) val , [Any](builtin-Any) tag)\] ref)

---

### calc_array_byteseq_size

```pony
fun box calc_array_byteseq_size(
  array: Array[(String val | Array[U8 val] val)] val)
: USize val
```
#### Parameters

*   array: [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val

#### Returns

* [USize](builtin-USize) val

---

### send_topic_message

```pony
fun ref send_topic_message(
  topic: String val,
  opaque: Any tag,
  value: (String val | Array[U8 val] val | Array[(String val | Array[U8 val] val)] val),
  key: (None val | String val | Array[U8 val] val | 
    Array[(String val | Array[U8 val] val)] val) = seq,
  ts: (I64 val | None val) = seq)
: (None val | (KafkaError val , I32 val , Any tag))
```
#### Parameters

*   topic: [String](builtin-String) val
*   opaque: [Any](builtin-Any) tag
*   value: ([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val | [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val)
*   key: ([None](builtin-None) val | [String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val | 
    [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val) = seq
*   ts: ([I64](builtin-I64) val | [None](builtin-None) val) = seq

#### Returns

* ([None](builtin-None) val | ([KafkaError](pony-kafka-KafkaError) val , [I32](builtin-I32) val , [Any](builtin-Any) tag))

---

