# TimerNotify

Notifications for timer.


```pony
interface ref TimerNotify
```

## Public Functions

### apply

Called with the the number of times the timer has fired since this was last
called. Usually, the value of `count` will be 1. If it is not 1, it means
that the timer isn't firing on schedule.

For example, if your timer is set to fire every 10 milliseconds, and
`count` is 2, that means it has been between 20-29 milliseconds since the
last time your timer fired. Non 1 values for a timer are rare and indicate
a system under heavy load.

Return true to reschedule the timer (if it has an interval), or
false to cancel the timer (even if it has an interval).


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

Called if the timer is cancelled. This is also called if the notifier
returns false from its `apply` method.


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

