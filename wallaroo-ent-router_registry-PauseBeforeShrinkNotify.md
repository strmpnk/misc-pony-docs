# PauseBeforeShrinkNotify

```pony
class ref PauseBeforeShrinkNotify is
  TimerNotify ref
```

#### Implements

* [TimerNotify](time-TimerNotify) ref

---

## Constructors

### create

```pony
new iso create(
  auth: AmbientAuth val,
  worker_name: String val,
  connections: Connections tag,
  remaining_workers: Array[String val] val,
  leaving_workers: Array[String val] val)
: PauseBeforeShrinkNotify iso^
```
#### Parameters

*   auth: [AmbientAuth](builtin-AmbientAuth) val
*   worker_name: [String](builtin-String) val
*   connections: [Connections](wallaroo-ent-network-Connections) tag
*   remaining_workers: [Array](builtin-Array)\[[String](builtin-String) val\] val
*   leaving_workers: [Array](builtin-Array)\[[String](builtin-String) val\] val

#### Returns

* [PauseBeforeShrinkNotify](wallaroo-ent-router_registry-PauseBeforeShrinkNotify) iso^

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

