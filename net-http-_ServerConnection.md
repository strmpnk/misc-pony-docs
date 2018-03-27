# _ServerConnection

Manages a stream of requests coming into a server from a single client,
dispatches those request to a back-end, and returns the responses back
to the client.


```pony
actor tag _ServerConnection is
  HTTPSession tag
```

#### Implements

* [HTTPSession](net-http-HTTPSession) tag

---

## Constructors

### create

```pony
new tag create(
  handlermaker: HandlerFactory val,
  logger: Logger val,
  conn: TCPConnection tag,
  client_ip: String val)
: _ServerConnection tag^
```
#### Parameters

*   handlermaker: [HandlerFactory](net-http-HandlerFactory) val
*   logger: [Logger](net-http-Logger) val
*   conn: [TCPConnection](net-TCPConnection) tag
*   client_ip: [String](builtin-String) val

#### Returns

* [_ServerConnection](net-http-_ServerConnection) tag^

---

## Public Behaviours

### dispose

Close the connection from the server end.


```pony
be dispose()
```

---

### cancel

Cancel the current response. The connection has closed.


```pony
be cancel(
  msg: Payload val)
```
#### Parameters

*   msg: [Payload](net-http-Payload) val

---

### apply

Initiate transmission of the HTTP Response message for the current
Request.


```pony
be apply(
  response: Payload val)
```
#### Parameters

*   response: [Payload](net-http-Payload) val

---

### write

Write low level outbound raw byte stream.


```pony
be write(
  data: (String val | Array[U8 val] val))
```
#### Parameters

*   data: ([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)

---

### finish

We are done sending a response. We can close the connection if
`keepalive` was not requested.


```pony
be finish()
```

---

### throttled

TCP connection can not accept data for a while.


```pony
be throttled()
```

---

### unthrottled

TCP connection can not accept data for a while.


```pony
be unthrottled()
```

---

## Private Behaviours

### _deliver

Dispatch requests. At the time this behavior is called for StreamTransfer
and ChunkTransfer encodings, only the headers of the request may have
been received. Receiving and dealing with the body, which could be
quite large in POST methods, is up to the chosen application handler.

The client can send several requests without waiting for a response,
but they are only passed to the back end one at a time. Only when all
of the response to a processed request has been sent is the next request
processed.


```pony
be _deliver(
  request: Payload val)
```
#### Parameters

*   request: [Payload](net-http-Payload) val

---

### _chunk

Receive some `request` body data, which we pass on to the handler.


```pony
be _chunk(
  data: (String val | Array[U8 val] val))
```
#### Parameters

*   data: ([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)

---

### _finish

Inidcates that the last *inbound* body chunk has been sent to
`_chunk`. This is passed on to the back end.


```pony
be _finish()
```

---

### _closed

```pony
be _closed()
```

---

### _mute

```pony
be _mute()
```

---

### _unmute

```pony
be _unmute()
```

---

## Private Functions

### _dispatch_pending

If we have pending requests, dispatch the next one.


```pony
fun ref _dispatch_pending()
: None val
```

#### Returns

* [None](builtin-None) val

---

### _send

Send a single response.


```pony
fun ref _send(
  response: Payload val)
: None val
```
#### Parameters

*   response: [Payload](net-http-Payload) val

#### Returns

* [None](builtin-None) val

---

