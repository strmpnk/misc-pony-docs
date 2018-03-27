# KafkaNetworkSniffer

```pony
trait ref KafkaNetworkSniffer
```

## Public Behaviours

### data_sent

```pony
be data_sent(
  broker_id: I32 val,
  data: ByteSeqIter val)
```
#### Parameters

*   broker_id: [I32](builtin-I32) val
*   data: [ByteSeqIter](builtin-ByteSeqIter) val

---

### data_received

```pony
be data_received(
  broker_id: I32 val,
  data: Array[U8 val] iso)
```
#### Parameters

*   broker_id: [I32](builtin-I32) val
*   data: [Array](builtin-Array)\[[U8](builtin-U8) val\] iso

---

