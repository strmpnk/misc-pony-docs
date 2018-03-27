# _KafkaRefreshMetadataTimerNotify

```pony
class ref _KafkaRefreshMetadataTimerNotify is
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
: _KafkaRefreshMetadataTimerNotify iso^
```
#### Parameters

*   conn: [KafkaBrokerConnection](pony-kafka-KafkaBrokerConnection) tag

#### Returns

* [_KafkaRefreshMetadataTimerNotify](pony-kafka-_KafkaRefreshMetadataTimerNotify) iso^

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

