# DataGen

```pony
primitive val DataGen
```

## Constructors

### create

```pony
new val create()
: DataGen val^
```

#### Returns

* [DataGen](pony-kafka-DataGen) val^

---

## Public Functions

### generate_data

```pony
fun box generate_data(
  p: KafkaProducer tag = seq)
: HashMap[String val, HashMap[I32 val, Array[ProducerKafkaMessage val] ref, HashEq[I32 val] val] ref, HashEq[String val] val] ref
```
#### Parameters

*   p: [KafkaProducer](pony-kafka-KafkaProducer) tag = seq

#### Returns

* [HashMap](collections-HashMap)\[[String](builtin-String) val, [HashMap](collections-HashMap)\[[I32](builtin-I32) val, [Array](builtin-Array)\[[ProducerKafkaMessage](pony-kafka-ProducerKafkaMessage) val\] ref, [HashEq](collections-HashEq)\[[I32](builtin-I32) val\] val\] ref, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] ref

---

### generate_random_data

```pony
fun box generate_random_data(
  topic: String val,
  msg_size: USize val,
  num_msgs: USize val,
  p: KafkaProducer tag = seq)
: HashMap[I32 val, Array[ProducerKafkaMessage val] iso, HashEq[I32 val] val] val ?
```
#### Parameters

*   topic: [String](builtin-String) val
*   msg_size: [USize](builtin-USize) val
*   num_msgs: [USize](builtin-USize) val
*   p: [KafkaProducer](pony-kafka-KafkaProducer) tag = seq

#### Returns

* [HashMap](collections-HashMap)\[[I32](builtin-I32) val, [Array](builtin-Array)\[[ProducerKafkaMessage](pony-kafka-ProducerKafkaMessage) val\] iso, [HashEq](collections-HashEq)\[[I32](builtin-I32) val\] val\] val ?

---

### eq

```pony
fun box eq(
  that: DataGen val)
: Bool val
```
#### Parameters

*   that: [DataGen](pony-kafka-DataGen) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: DataGen val)
: Bool val
```
#### Parameters

*   that: [DataGen](pony-kafka-DataGen) val

#### Returns

* [Bool](builtin-Bool) val

---

