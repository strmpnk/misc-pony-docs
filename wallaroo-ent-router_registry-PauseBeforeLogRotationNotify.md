# PauseBeforeLogRotationNotify

```pony
class ref PauseBeforeLogRotationNotify is
  TimerNotify ref
```

#### Implements

* [TimerNotify](time-TimerNotify) ref

---

## Constructors

### create

```pony
new iso create(
  registry: RouterRegistry tag)
: PauseBeforeLogRotationNotify iso^
```
#### Parameters

*   registry: [RouterRegistry](wallaroo-ent-router_registry-RouterRegistry) tag

#### Returns

* [PauseBeforeLogRotationNotify](wallaroo-ent-router_registry-PauseBeforeLogRotationNotify) iso^

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

