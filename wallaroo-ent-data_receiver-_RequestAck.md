# _RequestAck

```pony
class ref _RequestAck is
  TimerNotify ref
```

#### Implements

* [TimerNotify](time-TimerNotify) ref

---

## Constructors

### create

```pony
new iso create(
  d: DataReceiver tag)
: _RequestAck iso^
```
#### Parameters

*   d: [DataReceiver](wallaroo-ent-data_receiver-DataReceiver) tag

#### Returns

* [_RequestAck](wallaroo-ent-data_receiver-_RequestAck) iso^

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

