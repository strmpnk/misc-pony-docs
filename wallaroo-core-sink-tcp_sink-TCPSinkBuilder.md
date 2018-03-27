# TCPSinkBuilder

```pony
class val TCPSinkBuilder
```

## Constructors

### create

```pony
new val create(
  encoder_wrapper: TCPEncoderWrapper val,
  host: String val,
  service: String val,
  initial_msgs: Array[Array[(String val | Array[U8 val] val)] val] val)
: TCPSinkBuilder val^
```
#### Parameters

*   encoder_wrapper: [TCPEncoderWrapper](wallaroo-core-sink-tcp_sink-TCPEncoderWrapper) val
*   host: [String](builtin-String) val
*   service: [String](builtin-String) val
*   initial_msgs: [Array](builtin-Array)\[[Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val\] val

#### Returns

* [TCPSinkBuilder](wallaroo-core-sink-tcp_sink-TCPSinkBuilder) val^

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

