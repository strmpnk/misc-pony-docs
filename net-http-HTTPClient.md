# HTTPClient

Manages a group of HTTP connections on behalf of a client application.
A client should create one instance of this class.


```pony
class ref HTTPClient
```

## Constructors

### create

```pony
new ref create(
  auth: (AmbientAuth val | NetAuth val | TCPAuth val | 
    TCPConnectAuth val),
  sslctx: (SSLContext val | None val) = seq,
  pipeline: Bool val = seq)
: HTTPClient ref^
```
#### Parameters

*   auth: ([AmbientAuth](builtin-AmbientAuth) val | [NetAuth](net-NetAuth) val | [TCPAuth](net-TCPAuth) val | 
    [TCPConnectAuth](net-TCPConnectAuth) val)
*   sslctx: ([SSLContext](net-ssl-SSLContext) val | [None](builtin-None) val) = seq
*   pipeline: [Bool](builtin-Bool) val = seq

#### Returns

* [HTTPClient](net-http-HTTPClient) ref^

---

## Public Functions

### apply

Schedule a request on an HTTP session. If a new connection is created,
a new instance of the application's Receive Handler will be created
for it. A `val` copy of the `Payload` is returned, and it can not be
modified after this point.
This is useful in Stream and Chunked transfer modes, so that the
application can follow up with calls to `Client.send_body`.


```pony
fun ref apply(
  request: Payload trn,
  handlermaker: HandlerFactory val)
: Payload val ?
```
#### Parameters

*   request: [Payload](net-http-Payload) trn
*   handlermaker: [HandlerFactory](net-http-HandlerFactory) val

#### Returns

* [Payload](net-http-Payload) val ?

---

### dispose

Disposes the sessions and cancels all pending requests.


```pony
fun ref dispose()
: None val
```

#### Returns

* [None](builtin-None) val

---

### send_body

```pony
fun ref send_body(
  data: (String val | Array[U8 val] val),
  session: HTTPSession tag)
: None val
```
#### Parameters

*   data: ([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)
*   session: [HTTPSession](net-http-HTTPSession) tag

#### Returns

* [None](builtin-None) val

---

## Private Functions

### _get_session

Gets or creates an HTTP Session for the given URL. If a new session
is created, a new Receive Handler instance is created too.


```pony
fun ref _get_session(
  url: URL val,
  handlermaker: HandlerFactory val)
: _ClientConnection tag ?
```
#### Parameters

*   url: [URL](net-http-URL) val
*   handlermaker: [HandlerFactory](net-http-HandlerFactory) val

#### Returns

* [_ClientConnection](net-http-_ClientConnection) tag ?

---

