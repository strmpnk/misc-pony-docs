# _ClientConnection

Manages a persistent and possibly pipelined TCP connection to an HTTP server.

This is where pipelining happens, if it has been enabled by the `Client`.
Only "safe" requests (GET, HEAD, OPTIONS) are sent to the server if
*any* responses are still pending.

The `HTTPHandler.send_body` notification function will be called if/when
the `HTTPSession` is ready to receive body data for `POST` operations in
transfer modes other than `Oneshot`.

### Receiving Responses

Reception is handled through an `HTTPHandler` instance.
`HTTPHandler.apply` signals the arrival of a message with headers.
How the body data is obtained depends on the `transfer` mode.

* For `StreamTranfer` and `ChunkedTransfer` modes, there will be
any number of `HTTPHandler.chunk` notifications, followed by
an `HTTPHandler.finished` notification.

* For `OneShotTransfer` mode, the client application just needs to
call `Payload.body` once to get the entire body.

## The HandlerFactory

The `Client` class will try to re-use sessions. If it needs to create
a new session, based on the request URL, it will do that, and then it
will need a new instance of the caller's `HTTPHandler` class.
Since the client application code does not know in advance when this
 will be necessary, it passes in a `HandlerFactory` that creates the
actual `HTTPHandler`, customized
for the client application's needs.


```pony
actor tag _ClientConnection is
  HTTPSession tag
```

#### Implements

* [HTTPSession](net-http-HTTPSession) tag

---

## Constructors

### create

```pony
new tag create(
  auth: (AmbientAuth val | NetAuth val | TCPAuth val | 
    TCPConnectAuth val),
  host: String val,
  service: String val,
  sslctx: (SSLContext val | None val) = seq,
  pipeline: Bool val = seq,
  handlermaker: HandlerFactory val)
: _ClientConnection tag^
```
#### Parameters

*   auth: ([AmbientAuth](builtin-AmbientAuth) val | [NetAuth](net-NetAuth) val | [TCPAuth](net-TCPAuth) val | 
    [TCPConnectAuth](net-TCPConnectAuth) val)
*   host: [String](builtin-String) val
*   service: [String](builtin-String) val
*   sslctx: ([SSLContext](net-ssl-SSLContext) val | [None](builtin-None) val) = seq
*   pipeline: [Bool](builtin-Bool) val = seq
*   handlermaker: [HandlerFactory](net-http-HandlerFactory) val

#### Returns

* [_ClientConnection](net-http-_ClientConnection) tag^

---

## Public Behaviours

### apply

Schedule a request to be sent by adding it to the `unsent` queue
for this session.


```pony
be apply(
  request: Payload val)
```
#### Parameters

*   request: [Payload](net-http-Payload) val

---

### cancel

Cancel a request.


```pony
be cancel(
  request: Payload val)
```
#### Parameters

*   request: [Payload](net-http-Payload) val

---

### write

Write a low-level byte stream. The `Payload` objects call this to
generate their wire representation.


```pony
be write(
  data: (String val | Array[U8 val] val))
```
#### Parameters

*   data: ([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)

---

### finish

We are done sending a request with a long body.


```pony
be finish()
```

---

### dispose

Cancels all requests and disposes the tcp connection.


```pony
be dispose()
```

---

### throttled

The connection to the server can not accept data for a while.
We set a local flag too so we do not send anything on the queue.


```pony
be throttled()
```

---

### unthrottled

The connection to the server can now accept more data.


```pony
be unthrottled()
```

---

## Private Behaviours

### _deliver

Deal with a new Response coming back from the server.

Since the session operates in a FIFO manner, the Request corresponding
to this Response is the oldest one on the `_sent` list. We take it
off that list and call its handler. It becomes the 'currently being
delivered' response and subsequent body data has to go there as well,
if there is any.


```pony
be _deliver(
  response: Payload val)
```
#### Parameters

*   response: [Payload](net-http-Payload) val

---

### _connected

The connection to the server has been established. Send pending requests.


```pony
be _connected(
  conn: TCPConnection tag)
```
#### Parameters

*   conn: [TCPConnection](net-TCPConnection) tag

---

### _connect_failed

The connection couldn't be established. Cancel all pending requests.


```pony
be _connect_failed(
  conn: TCPConnection tag)
```
#### Parameters

*   conn: [TCPConnection](net-TCPConnection) tag

---

### _auth_failed

The connection couldn't be authenticated. Cancel all pending requests.


```pony
be _auth_failed(
  conn: TCPConnection tag)
```
#### Parameters

*   conn: [TCPConnection](net-TCPConnection) tag

---

### _closed

The connection to the server has closed prematurely. Cancel everything.


```pony
be _closed(
  conn: TCPConnection tag)
```
#### Parameters

*   conn: [TCPConnection](net-TCPConnection) tag

---

### _chunk

Called when *inbound* body data has arrived for the currently
inbound `Payload`. This should be passed directly to the application's
`HTTPHandler.chunk` method.


```pony
be _chunk(
  data: (String val | Array[U8 val] val))
```
#### Parameters

*   data: ([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)

---

### _finish

Indicates that the last *inbound* body chunk has been sent to
`_chunk`. This is passed on to the front end.

_send_pending is called to detect that _unsent and _sent are emptye
and that _conn can be disposed. 


```pony
be _finish()
```

---

### _mute

The application can not handle any more data for a while.


```pony
be _mute()
```

---

### _unmute

The application can accept more data.


```pony
be _unmute()
```

---

## Private Functions

### _send_pending

Send pending requests to the server. If the connection is closed,
open it. If we have nothing to send and we aren't waiting on any
responses, close the connection.


```pony
fun ref _send_pending()
: None val
```

#### Returns

* [None](builtin-None) val

---

### _new_conn

Creates a new connection. `ResponseBuilder` is the notification class
that will send back a `_connected` call when the connection has been made.


```pony
fun ref _new_conn()
: None val
```

#### Returns

* [None](builtin-None) val

---

### _cancel_all

Cancel all pending requests.


```pony
fun ref _cancel_all()
: None val
```

#### Returns

* [None](builtin-None) val

---

