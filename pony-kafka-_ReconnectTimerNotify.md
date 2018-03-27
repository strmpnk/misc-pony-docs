# _ReconnectTimerNotify

```pony
class ref _ReconnectTimerNotify is
  TimerNotify ref
```

#### Implements

* [TimerNotify](time-TimerNotify) ref

---

## Constructors

### create

```pony
new iso create(
  conn: CustomTCPConnection tag)
: _ReconnectTimerNotify iso^
```
#### Parameters

*   conn: [CustomTCPConnection](.-customnet-CustomTCPConnection) tag

#### Returns

* [_ReconnectTimerNotify](pony-kafka-_ReconnectTimerNotify) iso^

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

