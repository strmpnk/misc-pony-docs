# KafkaSinkConfig\[Out: [Any](builtin-Any) val\]

```pony
class val KafkaSinkConfig[Out: Any val] is
  SinkConfig[Out] val
```

#### Implements

* [SinkConfig](wallaroo-core-sink-SinkConfig)\[Out\] val

---

## Constructors

### create

```pony
new val create(
  encoder: KafkaSinkEncoder[Out] val,
  ksco: KafkaConfigOptions iso,
  auth: (AmbientAuth val | NetAuth val | TCPAuth val | 
    TCPConnectAuth val))
: KafkaSinkConfig[Out] val^
```
#### Parameters

*   encoder: [KafkaSinkEncoder](wallaroo-core-sink-kafka_sink-KafkaSinkEncoder)\[Out\] val
*   ksco: [KafkaConfigOptions](pony-kafka-KafkaConfigOptions) iso
*   auth: ([AmbientAuth](builtin-AmbientAuth) val | [NetAuth](net-NetAuth) val | [TCPAuth](net-TCPAuth) val | 
    [TCPConnectAuth](net-TCPConnectAuth) val)

#### Returns

* [KafkaSinkConfig](wallaroo-core-sink-kafka_sink-KafkaSinkConfig)\[Out\] val^

---

## Public Functions

### apply

```pony
fun box apply()
: SinkBuilder val
```

#### Returns

* [SinkBuilder](wallaroo-core-sink-SinkBuilder) val

---

