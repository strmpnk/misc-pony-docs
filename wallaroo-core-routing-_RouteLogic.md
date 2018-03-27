# _RouteLogic

```pony
class ref _RouteLogic is
  RouteLogic ref
```

#### Implements

* [RouteLogic](wallaroo-core-routing-RouteLogic) ref

---

## Constructors

### create

```pony
new ref create(
  step: Producer ref,
  consumer: Consumer tag,
  r_type: String val)
: _RouteLogic ref^
```
#### Parameters

*   step: [Producer](wallaroo-core-common-Producer) ref
*   consumer: [Consumer](wallaroo-core-common-Consumer) tag
*   r_type: [String](builtin-String) val

#### Returns

* [_RouteLogic](wallaroo-core-routing-_RouteLogic) ref^

---

## Public Functions

### application_initialized

```pony
fun ref application_initialized(
  step_type: String val)
: None val
```
#### Parameters

*   step_type: [String](builtin-String) val

#### Returns

* [None](builtin-None) val

---

### dispose

Return unused credits to downstream consumer


```pony
fun ref dispose()
: None val
```

#### Returns

* [None](builtin-None) val

---

## Private Functions

### _report_ready_to_work

```pony
fun ref _report_ready_to_work()
: None val
```

#### Returns

* [None](builtin-None) val

---

