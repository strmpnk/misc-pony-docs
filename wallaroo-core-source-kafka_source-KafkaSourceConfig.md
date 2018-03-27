# KafkaSourceConfig\[In: [Any](builtin-Any) val\]

```pony
class val KafkaSourceConfig[In: Any val] is
  SourceConfig[In] val
```

#### Implements

* [SourceConfig](wallaroo-core-source-SourceConfig)\[In\] val

---

## Constructors

### create

```pony
new val create(
  ksco: KafkaConfigOptions iso,
  auth: (AmbientAuth val | NetAuth val | TCPAuth val | 
    TCPConnectAuth val),
  handler: SourceHandler[In] val)
: KafkaSourceConfig[In] val^
```
#### Parameters

*   ksco: [KafkaConfigOptions](pony-kafka-KafkaConfigOptions) iso
*   auth: ([AmbientAuth](builtin-AmbientAuth) val | [NetAuth](net-NetAuth) val | [TCPAuth](net-TCPAuth) val | 
    [TCPConnectAuth](net-TCPConnectAuth) val)
*   handler: [SourceHandler](wallaroo-core-source-SourceHandler)\[In\] val

#### Returns

* [KafkaSourceConfig](wallaroo-core-source-kafka_source-KafkaSourceConfig)\[In\] val^

---

## Public Functions

### source_listener_builder_builder

```pony
fun box source_listener_builder_builder()
: KafkaSourceListenerBuilderBuilder[In] val
```

#### Returns

* [KafkaSourceListenerBuilderBuilder](wallaroo-core-source-kafka_source-KafkaSourceListenerBuilderBuilder)\[In\] val

---

### source_builder

```pony
fun box source_builder(
  app_name: String val,
  name: String val)
: KafkaSourceBuilderBuilder[In] val
```
#### Parameters

*   app_name: [String](builtin-String) val
*   name: [String](builtin-String) val

#### Returns

* [KafkaSourceBuilderBuilder](wallaroo-core-source-kafka_source-KafkaSourceBuilderBuilder)\[In\] val

---

