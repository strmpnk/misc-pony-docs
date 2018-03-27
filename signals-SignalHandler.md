# SignalHandler

Listen for a specific signal.


```pony
actor tag SignalHandler
```

## Constructors

### create

Create a signal handler.


```pony
new tag create(
  notify: SignalNotify iso,
  sig: U32 val)
: SignalHandler tag^
```
#### Parameters

*   notify: [SignalNotify](signals-SignalNotify) iso
*   sig: [U32](builtin-U32) val

#### Returns

* [SignalHandler](signals-SignalHandler) tag^

---

## Public Behaviours

### raise

Raise the signal.


```pony
be raise()
```

---

### dispose

Dispose of the signal handler.


```pony
be dispose()
```

---

## Private Behaviours

### _event_notify

Called when the signal is received, or when the AsioEventID can be
destroyed.


```pony
be _event_notify(
  event: Pointer[AsioEvent val] tag,
  flags: U32 val,
  arg: U32 val)
```
#### Parameters

*   event: [Pointer](builtin-Pointer)\[[AsioEvent](builtin-AsioEvent) val\] tag
*   flags: [U32](builtin-U32) val
*   arg: [U32](builtin-U32) val

---

## Private Functions

### _dispose

Dispose of the AsioEventID.


```pony
fun ref _dispose()
: None val
```

#### Returns

* [None](builtin-None) val

---

