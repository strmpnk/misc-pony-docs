# _KafkaSendPendingMessagesTimerNotify

```pony
class ref _KafkaSendPendingMessagesTimerNotify is
  TimerNotify ref
```

#### Implements

* [TimerNotify](time-TimerNotify) ref

---

## Constructors

### create

```pony
new iso create(
  conn: KafkaBrokerConnection tag)
: _KafkaSendPendingMessagesTimerNotify iso^
```
#### Parameters

*   conn: [KafkaBrokerConnection](pony-kafka-KafkaBrokerConnection) tag

#### Returns

* [_KafkaSendPendingMessagesTimerNotify](pony-kafka-_KafkaSendPendingMessagesTimerNotify) iso^

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

