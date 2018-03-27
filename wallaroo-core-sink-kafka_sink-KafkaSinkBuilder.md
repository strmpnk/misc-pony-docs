# KafkaSinkBuilder

```pony
class val KafkaSinkBuilder
```

## Constructors

### create

```pony
new val create(
  encoder_wrapper: KafkaEncoderWrapper val,
  ksco: KafkaConfigOptions val,
  auth: (AmbientAuth val | NetAuth val | TCPAuth val | 
    TCPConnectAuth val))
: KafkaSinkBuilder val^
```
#### Parameters

*   encoder_wrapper: [KafkaEncoderWrapper](wallaroo-core-sink-kafka_sink-KafkaEncoderWrapper) val
*   ksco: [KafkaConfigOptions](pony-kafka-KafkaConfigOptions) val
*   auth: ([AmbientAuth](builtin-AmbientAuth) val | [NetAuth](net-NetAuth) val | [TCPAuth](net-TCPAuth) val | 
    [TCPConnectAuth](net-TCPConnectAuth) val)

#### Returns

* [KafkaSinkBuilder](wallaroo-core-sink-kafka_sink-KafkaSinkBuilder) val^

---

## Public Functions

### apply

```pony
fun box apply(
  reporter: MetricsReporter iso,
  env: Env val)
: (Consumer tag & DisposableActor tag)
```
#### Parameters

*   reporter: [MetricsReporter](wallaroo-core-metrics-MetricsReporter) iso
*   env: [Env](builtin-Env) val

#### Returns

* ([Consumer](wallaroo-core-common-Consumer) tag & [DisposableActor](builtin-DisposableActor) tag)

---

