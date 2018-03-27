# PauseBeforeReconnectTCPSink

```pony
class ref PauseBeforeReconnectTCPSink is
  TimerNotify ref
```

#### Implements

* [TimerNotify](time-TimerNotify) ref

---

## Constructors

### create

```pony
new iso create(
  tcp_sink: TCPSink tag)
: PauseBeforeReconnectTCPSink iso^
```
#### Parameters

*   tcp_sink: [TCPSink](wallaroo-core-sink-tcp_sink-TCPSink) tag

#### Returns

* [PauseBeforeReconnectTCPSink](wallaroo-core-sink-tcp_sink-PauseBeforeReconnectTCPSink) iso^

---

## Public Functions

### apply

```pony
fun ref apply(
  timer: Timer ref,
  count: U64 val)
: Bool val
```
#### Parameters

*   timer: [Timer](time-Timer) ref
*   count: [U64](builtin-U64) val

#### Returns

* [Bool](builtin-Bool) val

---

### cancel

```pony
fun ref cancel(
  timer: Timer ref)
: None val
```
#### Parameters

*   timer: [Timer](time-Timer) ref

#### Returns

* [None](builtin-None) val

---

