# HTTPHandler

This is the interface through which HTTP messages are delivered *to*
application code. On the server, this will be HTTP Requests (GET,
HEAD, DELETE, POST, etc) sent from a client. On the client, this will
be the HTTP Responses coming back from the server. The protocol is largely
symmetrical and the same interface definition is used, though what
processing happens behind the interface will of course vary.

This interface delivers asynchronous events when receiving an HTTP
message (called a `Payload`). Calls to these methods are made in
the context of the `HTTPSession` actor so most of them should be
passing data on to a processing actor.

Each `HTTPSession` must have a unique instance of the handler. The
application code does not necessarily know when an `HTTPSession` is created,
so the application must provide an instance of `HandlerFactory` that
will be called at the appropriate time.


```pony
interface ref HTTPHandler
```

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

