# TypedRoute\[In: [Any](builtin-Any) val\]

Relationship between a single producer and a single consumer.


```pony
class ref TypedRoute[In: Any val] is
  Route ref
```

#### Implements

* [Route](wallaroo-core-routing-Route) ref

---

## Constructors

### create

```pony
new ref create(
  step: Producer ref,
  consumer: Consumer tag,
  metrics_reporter: MetricsReporter ref)
: TypedRoute[In] ref^
```
#### Parameters

*   step: [Producer](wallaroo-core-common-Producer) ref
*   consumer: [Consumer](wallaroo-core-common-Consumer) tag
*   metrics_reporter: [MetricsReporter](wallaroo-core-metrics-MetricsReporter) ref

#### Returns

* [TypedRoute](wallaroo-core-routing-TypedRoute)\[In\] ref^

---

## Public Functions

### application_created

```pony
fun ref application_created()
: None val
```

#### Returns

* [None](builtin-None) val

---

### application_initialized

```pony
fun ref application_initialized(
  step_type: String val)
: None val
```
#### Parameters

*   step_type: [String](builtin-String) val

#### Returns

* [None](builtin-None) val

---

### id

```pony
fun box id()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### dispose

```pony
fun ref dispose()
: None val
```

#### Returns

* [None](builtin-None) val

---

### run\[D: D\]

```pony
fun ref run[D: D](
  metric_name: String val,
  pipeline_time_spent: U64 val,
  data: D,
  cfp: Producer ref,
  msg_uid: U128 val,
  frac_ids: (Array[U32 val] val | None val),
  latest_ts: U64 val,
  metrics_id: U16 val,
  worker_ingress_ts: U64 val)
: None val
```
#### Parameters

*   metric_name: [String](builtin-String) val
*   pipeline_time_spent: [U64](builtin-U64) val
*   data: D
*   cfp: [Producer](wallaroo-core-common-Producer) ref
*   msg_uid: [U128](builtin-U128) val
*   frac_ids: ([Array](builtin-Array)\[[U32](builtin-U32) val\] val | [None](builtin-None) val)
*   latest_ts: [U64](builtin-U64) val
*   metrics_id: [U16](builtin-U16) val
*   worker_ingress_ts: [U64](builtin-U64) val

#### Returns

* [None](builtin-None) val

---

### forward

```pony
fun ref forward(
  delivery_msg: ReplayableDeliveryMsg val,
  pipeline_time_spent: U64 val,
  cfp: Producer ref,
  latest_ts: U64 val,
  metrics_id: U16 val,
  metric_name: String val,
  worker_ingress_ts: U64 val)
: None val
```
#### Parameters

*   delivery_msg: [ReplayableDeliveryMsg](wallaroo-core-messages-ReplayableDeliveryMsg) val
*   pipeline_time_spent: [U64](builtin-U64) val
*   cfp: [Producer](wallaroo-core-common-Producer) ref
*   latest_ts: [U64](builtin-U64) val
*   metrics_id: [U16](builtin-U16) val
*   metric_name: [String](builtin-String) val
*   worker_ingress_ts: [U64](builtin-U64) val

#### Returns

* [None](builtin-None) val

---

### request_ack

```pony
fun ref request_ack()
: None val
```

#### Returns

* [None](builtin-None) val

---

## Private Functions

### _send_message_on_route

```pony
fun ref _send_message_on_route(
  metric_name: String val,
  pipeline_time_spent: U64 val,
  input: In,
  cfp: Producer ref,
  msg_uid: U128 val,
  frac_ids: (Array[U32 val] val | None val),
  latest_ts: U64 val,
  metrics_id: U16 val,
  worker_ingress_ts: U64 val)
: None val
```
#### Parameters

*   metric_name: [String](builtin-String) val
*   pipeline_time_spent: [U64](builtin-U64) val
*   input: In
*   cfp: [Producer](wallaroo-core-common-Producer) ref
*   msg_uid: [U128](builtin-U128) val
*   frac_ids: ([Array](builtin-Array)\[[U32](builtin-U32) val\] val | [None](builtin-None) val)
*   latest_ts: [U64](builtin-U64) val
*   metrics_id: [U16](builtin-U16) val
*   worker_ingress_ts: [U64](builtin-U64) val

#### Returns

* [None](builtin-None) val

---

