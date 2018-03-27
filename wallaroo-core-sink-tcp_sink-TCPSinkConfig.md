# TCPSinkConfig\[Out: [Any](builtin-Any) val\]

```pony
class val TCPSinkConfig[Out: Any val] is
  SinkConfig[Out] val
```

#### Implements

* [SinkConfig](wallaroo-core-sink-SinkConfig)\[Out\] val

---

## Constructors

### create

```pony
new val create(
  encoder: TCPSinkEncoder[Out] val,
  host: String val,
  service: String val,
  initial_msgs: Array[Array[(String val | Array[U8 val] val)] val] val = seq)
: TCPSinkConfig[Out] val^
```
#### Parameters

*   encoder: [TCPSinkEncoder](wallaroo-core-sink-tcp_sink-TCPSinkEncoder)\[Out\] val
*   host: [String](builtin-String) val
*   service: [String](builtin-String) val
*   initial_msgs: [Array](builtin-Array)\[[Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val\] val = seq

#### Returns

* [TCPSinkConfig](wallaroo-core-sink-tcp_sink-TCPSinkConfig)\[Out\] val^

---

### from_options

```pony
new val from_options(
  encoder: TCPSinkEncoder[Out] val,
  opts: TCPSinkConfigOptions val,
  initial_msgs: Array[Array[(String val | Array[U8 val] val)] val] val = seq)
: TCPSinkConfig[Out] val^
```
#### Parameters

*   encoder: [TCPSinkEncoder](wallaroo-core-sink-tcp_sink-TCPSinkEncoder)\[Out\] val
*   opts: [TCPSinkConfigOptions](wallaroo-core-sink-tcp_sink-TCPSinkConfigOptions) val
*   initial_msgs: [Array](builtin-Array)\[[Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val\] val = seq

#### Returns

* [TCPSinkConfig](wallaroo-core-sink-tcp_sink-TCPSinkConfig)\[Out\] val^

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

