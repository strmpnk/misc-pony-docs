# _KafkaPhaseDone

```pony
primitive val _KafkaPhaseDone is
  FsmState ref
```

#### Implements

* [FsmState](.-fsm-FsmState) ref

---

## Constructors

### create

```pony
new val create()
: _KafkaPhaseDone val^
```

#### Returns

* [_KafkaPhaseDone](pony-kafka-_KafkaPhaseDone) val^

---

## Public Functions

### string

```pony
fun box string()
: String val
```

#### Returns

* [String](builtin-String) val

---

### eq

```pony
fun box eq(
  that: _KafkaPhaseDone val)
: Bool val
```
#### Parameters

*   that: [_KafkaPhaseDone](pony-kafka-_KafkaPhaseDone) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: _KafkaPhaseDone val)
: Bool val
```
#### Parameters

*   that: [_KafkaPhaseDone](pony-kafka-_KafkaPhaseDone) val

#### Returns

* [Bool](builtin-Bool) val

---

