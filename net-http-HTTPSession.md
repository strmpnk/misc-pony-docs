# HTTPSession

An HTTP Session is the external API to the communication link
between client and server. A session can only transfer one message
at a time in each direction. The client and server each have their
own ways of implementing this interface, but to application code (either
in the client or in the server 'back end') this interface provides a
common view of how information is passed *into* the `net/http` package.


```pony
interface tag HTTPSession
```

## Public Behaviours

### apply

Start sending a request or response. The `Payload` must have all its
essential fields filled in at this point, because ownership is being
transferred to the session actor. This begins an outbound message.


```pony
be apply(
  payload: Payload val)
```
#### Parameters

*   payload: [Payload](net-http-Payload) val

---

### finish

Indicate that all *outbound* `add_chunk` calls have been made and
submission of the HTTP message is complete.


```pony
be finish()
```

---

### dispose

Close the connection from this end.


```pony
be dispose()
```

---

### write

Write raw byte stream to the outbound TCP connection.


```pony
be write(
  data: (String val | Array[U8 val] val))
```
#### Parameters

*   data: ([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)

---

### cancel

Tell the session to stop sending an *outbound* message.


```pony
be cancel(
  msg: Payload val)
```
#### Parameters

*   msg: [Payload](net-http-Payload) val

---

## Private Behaviours

### _mute

Stop delivering *incoming* data to the handler. This may not
be effective instantly.


```pony
be _mute()
```

---

### _unmute

Resume delivering incoming data to the handler.


```pony
be _unmute()
```

---

### _deliver

The appropriate Payload Builder will call this from the `TCPConnection`
actor to start delivery of a new *inbound* message. If the `Payload`s
`transfer_mode` is `OneshotTransfer`, this is the only notification 
that will happen for the message. Otherwise there will be one or more
`_chunk` calls followed by a `_finish` call.


```pony
be _deliver(
  payload: Payload val)
```
#### Parameters

*   payload: [Payload](net-http-Payload) val

---

### _chunk

Deliver a piece of *inbound* body data to the application `HTTPHandler`
This is called by the PayloadBuilder.


```pony
be _chunk(
  data: (String val | Array[U8 val] val))
```
#### Parameters

*   data: ([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)

---

### _finish

Inidcates that the last *inbound* body chunk has been sent to
`_chunk`. This is called by the PayloadBuilder.


```pony
be _finish()
```

---

