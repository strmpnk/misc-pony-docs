# DeliveryMsg

```pony
trait val DeliveryMsg is
  ChannelMsg val
```

#### Implements

* [ChannelMsg](wallaroo-core-messages-ChannelMsg) val

---

## Public Functions

### target_id

```pony
fun box target_id()
: U128 val
```

#### Returns

* [U128](builtin-U128) val

---

### sender_name

```pony
fun box sender_name()
: String val
```

#### Returns

* [String](builtin-String) val

---

### deliver

```pony
fun box deliver(
  pipeline_time_spent: U64 val,
  target_step: Consumer tag,
  producer: Producer tag,
  seq_id: U64 val,
  route_id: U64 val,
  latest_ts: U64 val,
  metrics_id: U16 val,
  worker_ingress_ts: U64 val)
: Bool val
```
#### Parameters

*   pipeline_time_spent: [U64](builtin-U64) val
*   target_step: [Consumer](wallaroo-core-common-Consumer) tag
*   producer: [Producer](wallaroo-core-common-Producer) tag
*   seq_id: [U64](builtin-U64) val
*   route_id: [U64](builtin-U64) val
*   latest_ts: [U64](builtin-U64) val
*   metrics_id: [U16](builtin-U16) val
*   worker_ingress_ts: [U64](builtin-U64) val

#### Returns

* [Bool](builtin-Bool) val

---

