# DataMsg

```pony
class val DataMsg is
  ChannelMsg val
```

#### Implements

* [ChannelMsg](wallaroo-core-messages-ChannelMsg) val

---

## Constructors

### create

```pony
new val create(
  msg: ReplayableDeliveryMsg val,
  pipeline_time_spent': U64 val,
  seq_id': U64 val,
  latest_ts': U64 val,
  metrics_id': U16 val,
  metric_name': String val)
: DataMsg val^
```
#### Parameters

*   msg: [ReplayableDeliveryMsg](wallaroo-core-messages-ReplayableDeliveryMsg) val
*   pipeline_time_spent': [U64](builtin-U64) val
*   seq_id': [U64](builtin-U64) val
*   latest_ts': [U64](builtin-U64) val
*   metrics_id': [U16](builtin-U16) val
*   metric_name': [String](builtin-String) val

#### Returns

* [DataMsg](wallaroo-core-messages-DataMsg) val^

---

## Public fields

* let pipeline_time_spent: [U64](builtin-U64) val

---

* let seq_id: [U64](builtin-U64) val

---

* let delivery_msg: [ReplayableDeliveryMsg](wallaroo-core-messages-ReplayableDeliveryMsg) val

---

* let latest_ts: [U64](builtin-U64) val

---

* let metrics_id: [U16](builtin-U16) val

---

* let metric_name: [String](builtin-String) val

---

