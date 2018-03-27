# _PauseBeforeReconnect

```pony
class ref _PauseBeforeReconnect is
  TimerNotify ref
```

#### Implements

* [TimerNotify](time-TimerNotify) ref

---

## Constructors

### create

```pony
new iso create(
  metrics_sink: ReconnectingMetricsSink tag)
: _PauseBeforeReconnect iso^
```
#### Parameters

*   metrics_sink: [ReconnectingMetricsSink](wallaroo-core-metrics-ReconnectingMetricsSink) tag

#### Returns

* [_PauseBeforeReconnect](wallaroo-core-metrics-_PauseBeforeReconnect) iso^

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

