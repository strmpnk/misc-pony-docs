# _HTTPConnTestHandler

```pony
class ref _HTTPConnTestHandler is
  HTTPHandler ref
```

#### Implements

* [HTTPHandler](net-http-HTTPHandler) ref

---

## Constructors

### create

```pony
new ref create(
  h': TestHelper val)
: _HTTPConnTestHandler ref^
```
#### Parameters

*   h': [TestHelper](ponytest-TestHelper) val

#### Returns

* [_HTTPConnTestHandler](net-http-_HTTPConnTestHandler) ref^

---

## Public fields

* var n_received: [U32](builtin-U32) val

---

* let h: [TestHelper](ponytest-TestHelper) val

---

## Public Functions

### apply

```pony
fun ref apply(
  payload: Payload val)
: Any tag
```
#### Parameters

*   payload: [Payload](net-http-Payload) val

#### Returns

* [Any](builtin-Any) tag

---

### chunk

```pony
fun ref chunk(
  data: (String val | Array[U8 val] val))
: None val
```
#### Parameters

*   data: ([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)

#### Returns

* [None](builtin-None) val

---

### finished

```pony
fun ref finished()
: None val
```

#### Returns

* [None](builtin-None) val

---

### cancelled

```pony
fun ref cancelled()
: None val
```

#### Returns

* [None](builtin-None) val

---

### throttled

```pony
fun ref throttled()
: None val
```

#### Returns

* [None](builtin-None) val

---

### unthrottled

```pony
fun ref unthrottled()
: None val
```

#### Returns

* [None](builtin-None) val

---

### need_body

```pony
fun ref need_body()
: None val
```

#### Returns

* [None](builtin-None) val

---

