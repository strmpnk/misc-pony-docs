# KafkaClientManager

```pony
trait ref KafkaClientManager
```

## Public Behaviours

### receive_kafka_topics_partitions

```pony
be receive_kafka_topics_partitions(
  topic_partitions: HashMap[String val, ((KafkaConsumeOnly val | KafkaProduceOnly val | KafkaProduceAndConsume val) , HashSet[I32 val, HashEq[I32 val] val] ref), HashEq[String val] val] val)
```
#### Parameters

*   topic_partitions: [HashMap](collections-HashMap)\[[String](builtin-String) val, (([KafkaConsumeOnly](pony-kafka-KafkaConsumeOnly) val | [KafkaProduceOnly](pony-kafka-KafkaProduceOnly) val | [KafkaProduceAndConsume](pony-kafka-KafkaProduceAndConsume) val) , [HashSet](collections-HashSet)\[[I32](builtin-I32) val, [HashEq](collections-HashEq)\[[I32](builtin-I32) val\] val\] ref), [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val

---

### kafka_client_error

```pony
be kafka_client_error(
  error_report: KafkaErrorReport val)
```
#### Parameters

*   error_report: [KafkaErrorReport](pony-kafka-KafkaErrorReport) val

---

