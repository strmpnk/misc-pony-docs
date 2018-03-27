# _HTTPConnTestHandlerFactory

```pony
class val _HTTPConnTestHandlerFactory is
  HandlerFactory ref
```

#### Implements

* [HandlerFactory](net-http-HandlerFactory) ref

---

## Constructors

### create

```pony
new val create(
  h': TestHelper val)
: _HTTPConnTestHandlerFactory val^
```
#### Parameters

*   h': [TestHelper](ponytest-TestHelper) val

#### Returns

* [_HTTPConnTestHandlerFactory](net-http-_HTTPConnTestHandlerFactory) val^

---

## Public fields

* let h: [TestHelper](ponytest-TestHelper) val

---

## Public Functions

### apply

```pony
fun box apply(
  session: HTTPSession tag)
: HTTPHandler ref^
```
#### Parameters

*   session: [HTTPSession](net-http-HTTPSession) tag

#### Returns

* [HTTPHandler](net-http-HTTPHandler) ref^

---

