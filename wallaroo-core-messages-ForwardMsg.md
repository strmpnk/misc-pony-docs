# ForwardMsg\[D: [Any](builtin-Any) val\]

```pony
class val ForwardMsg[D: Any val] is
  ReplayableDeliveryMsg val
```

#### Implements

* [ReplayableDeliveryMsg](wallaroo-core-messages-ReplayableDeliveryMsg) val

---

## Constructors

### create

```pony
new val create(
  t_id: U128 val,
  from: String val,
  m_data: D,
  m_name: String val,
  proxy_address: ProxyAddress val,
  msg_uid': U128 val,
  frac_ids': (Array[U32 val] val | None val))
: ForwardMsg[D] val^
```
#### Parameters

*   t_id: [U128](builtin-U128) val
*   from: [String](builtin-String) val
*   m_data: D
*   m_name: [String](builtin-String) val
*   proxy_address: [ProxyAddress](wallaroo-core-topology-ProxyAddress) val
*   msg_uid': [U128](builtin-U128) val
*   frac_ids': ([Array](builtin-Array)\[[U32](builtin-U32) val\] val | [None](builtin-None) val)

#### Returns

* [ForwardMsg](wallaroo-core-messages-ForwardMsg)\[D\] val^

---

## Public Functions

### input

```pony
fun box input()
: Any val
```

#### Returns

* [Any](builtin-Any) val

---

### metric_name

```pony
fun box metric_name()
: String val
```

#### Returns

* [String](builtin-String) val

---

### msg_uid

```pony
fun box msg_uid()
: U128 val
```

#### Returns

* [U128](builtin-U128) val

---

### frac_ids

```pony
fun box frac_ids()
: (Array[U32 val] val | None val)
```

#### Returns

* ([Array](builtin-Array)\[[U32](builtin-U32) val\] val | [None](builtin-None) val)

---

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

### replay_deliver

```pony
fun box replay_deliver(
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

