# Payload

This class represent a single HTTP message, which can be either a
`request` or a `response`.

### Transfer Modes

HTTP provides two ways to encode the transmission of a message 'body',
of any size. This package supports both of them:

2. **StreamTransfer**. This is used for payload bodies where the exact
  length is known in advance, including most transfers of files. It is
  selected by calling `Payload.set_length` with an integer bytecount.
  Appication buffer sizes determine how much data is fed to the TCP
  connection at once, but the total amount must match this size.

3. **ChunkedTransfer**. This is used when the payload length can not be
  known in advance, but can be large. It is selected by calling
  `Payload.set_length` with a parameter of `None`. On the TCP link this mode
  can be detected because there is no `Content-Length` header at all, being
  replaced by the `Transfer-Encoding: chunked` header. In addition, the
  message body is separated into chunks, each with its own bytecount. As with
  `StreamTransfer` mode, transmission can be spread out over time with the
  difference that it is the original data source that determines the chunk
  size.

  If `Payload.set_length` is never called at all, a variation on
  `StreamTransfer` called `OneshotTransfer` is used. In this case, all of
  the message body is placed into the message at once, using
  `Payload.add_chunk` calls. The size will be determined when the message is
  submitted for transmission. Care must be taken not to consume too much
  memory, especially on a server where there can be multiple messages in
  transit at once.

  The type of transfer being used by an incoming message can be determined
  from its `transfer_mode` field, which will be one of the
  [TransferMode](net-http-TransferMode) types.

### Sequence

For example, to send a message of possibly large size:

1. Create the message with a call to `Payload.request` or `Payload.response`.
2. Set the `session` field of the message.
2. Call `Payload.set_length` to indicate the length of the body.
3. Add any additional headers that may be required, such as `Content-type`.
4. Submit the message for transmission by calling the either the
`HTTPSession.apply` method (in servers) or the `HTTPCLient.apply` method
in clients.
5. Wait for the `send_body` notification.
6. Make any number of calls to `Payload.send_chunk`.
7. Call `Payload.finish`.

To send a message of small, reasonable size (say, under 20KB), this
simplified method can be used instead:

1. Create the message with a call to `Payload.request` or `Payload.response`.
2. Set the `session` field of the message.
3. Add any additional headers that may be required, such as `Content-type`.
4. Call `add_chunk` one or more times to add body data.
4. Submit the message for transmission by calling the either the
[HTTPSession](net-http-HTTPSession)`.apply` method (in servers) or the
[HTTPClient](net-http-HTTPClient)`.apply` method in clients.


```pony
class trn Payload
```

## Constructors

### request

```pony
new iso request(
  method': String val = seq,
  url': URL val = seq)
: Payload iso^
```
#### Parameters

*   method': [String](builtin-String) val = seq
*   url': [URL](net-http-URL) val = seq

#### Returns

* [Payload](net-http-Payload) iso^

---

### response

```pony
new iso response(
  status': Status val = seq)
: Payload iso^
```
#### Parameters

*   status': [Status](net-http-Status) val = seq

#### Returns

* [Payload](net-http-Payload) iso^

---

### _empty

```pony
new iso _empty(
  response': Bool val = seq)
: Payload iso^
```
#### Parameters

*   response': [Bool](builtin-Bool) val = seq

#### Returns

* [Payload](net-http-Payload) iso^

---

## Public fields

* var proto: [String](builtin-String) val

---

* var status: [U16](builtin-U16) val

---

* var method: [String](builtin-String) val

---

* var url: [URL](net-http-URL) val

---

* var transfer_mode: ([ChunkedTransfer](net-http-ChunkedTransfer) val | [StreamTransfer](net-http-StreamTransfer) val | [OneshotTransfer](net-http-OneshotTransfer) val)

---

* var session: ([HTTPSession](net-http-HTTPSession) tag | [None](builtin-None) val)

---

* var username: [String](builtin-String) val

---

* var password: [String](builtin-String) val

---

## Public Functions

### apply

Get a header.


```pony
fun box apply(
  key: String val)
: String val ?
```
#### Parameters

*   key: [String](builtin-String) val

#### Returns

* [String](builtin-String) val ?

---

### is_safe

A request method is "safe" if it does not modify state in the resource.
These methods can be guaranteed not to have any body data.
Return true for a safe request method, false otherwise.


```pony
fun box is_safe()
: Bool val
```

#### Returns

* [Bool](builtin-Bool) val

---

### body

Get the body in `OneshotTransfer` mode.
In the other modes it raises an error.


```pony
fun box body()
: this->Array[(String val | Array[U8 val] val)] ref ?
```

#### Returns

* this->[Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] ref ?

---

### set_length

Set the body length when known in advance. This determines the
transfer mode that will be used. A parameter of 'None' will use
Chunked Transfer Encoding. A numeric value will use Streamed
transfer. Not calling this function at all will
use Oneshot transfer.


```pony
fun ref set_length(
  bytecount: (USize val | None val))
: None val
```
#### Parameters

*   bytecount: ([USize](builtin-USize) val | [None](builtin-None) val)

#### Returns

* [None](builtin-None) val

---

### update

Set any header. If we've already received the header, append the value as a
comma separated list, as per RFC 2616 section 4.2.


```pony
fun ref update(
  key: String val,
  value: String val)
: Payload ref^
```
#### Parameters

*   key: [String](builtin-String) val
*   value: [String](builtin-String) val

#### Returns

* [Payload](net-http-Payload) ref^

---

### headers

Get all the headers.


```pony
fun box headers()
: this->HashMap[String val, String val, HashEq[String val] val] ref
```

#### Returns

* this->[HashMap](collections-HashMap)\[[String](builtin-String) val, [String](builtin-String) val, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] ref

---

### body_size

Get the total intended size of the body.
`ServerConnection` accumulates actual size transferred for logging.


```pony
fun box body_size()
: (USize val | None val)
```

#### Returns

* ([USize](builtin-USize) val | [None](builtin-None) val)

---

### add_chunk

This is how application code adds data to the body in
`OneshotTransfer` mode. For large bodies, call `set_length`
and use `send_chunk` instead.


```pony
fun ref add_chunk(
  data: (String val | Array[U8 val] val))
: Payload ref^
```
#### Parameters

*   data: ([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)

#### Returns

* [Payload](net-http-Payload) ref^

---

### send_chunk

This is how application code sends body data in `StreamTransfer` and
`ChunkedTransfer` modes. For smaller body lengths, `add_chunk` in
`Oneshot` mode can be used instead.


```pony
fun box send_chunk(
  data: (String val | Array[U8 val] val))
: None val
```
#### Parameters

*   data: ([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)

#### Returns

* [None](builtin-None) val

---

### finish

Mark the end of body transmission. This does not do anything,
and is unnecessary, in Oneshot mode.


```pony
fun val finish()
: None val
```

#### Returns

* [None](builtin-None) val

---

### respond

Start sending a response from the server to the client.


```pony
fun val respond(
  response': Payload trn)
: None val
```
#### Parameters

*   response': [Payload](net-http-Payload) trn

#### Returns

* [None](builtin-None) val

---

### has_body

Determines whether a message has a body portion.


```pony
fun box has_body()
: Bool val
```

#### Returns

* [Bool](builtin-Bool) val

---

## Private Functions

### _client_fail

Start sending an error response.


```pony
fun val _client_fail()
: None val
```

#### Returns

* [None](builtin-None) val

---

### _write

Writes the payload to an HTTPSession. Requests and Responses differ
only in the first line of text - everything after that is the same format.


```pony
fun val _write(
  keepalive: Bool val = seq,
  conn: TCPConnection tag)
: None val
```
#### Parameters

*   keepalive: [Bool](builtin-Bool) val = seq
*   conn: [TCPConnection](net-TCPConnection) tag

#### Returns

* [None](builtin-None) val

---

### _write_request

Writes the 'request' parts of an HTTP message.


```pony
fun val _write_request(
  keepalive: Bool val,
  conn: TCPConnection tag)
: None val
```
#### Parameters

*   keepalive: [Bool](builtin-Bool) val
*   conn: [TCPConnection](net-TCPConnection) tag

#### Returns

* [None](builtin-None) val

---

### _write_common

Writes the parts of an HTTP message common to both requests and
responses.


```pony
fun val _write_common(
  conn: TCPConnection tag)
: None val
```
#### Parameters

*   conn: [TCPConnection](net-TCPConnection) tag

#### Returns

* [None](builtin-None) val

---

### _write_response

Write the response-specific parts of an HTTP message. This is the
status line, consisting of the protocol name, the status value,
and a string representation of the status (carried in the `method`
field). Since writing it out is an actor behavior call, we go to
the trouble of packaging it into a single string before sending.


```pony
fun val _write_response(
  keepalive: Bool val,
  conn: TCPConnection tag)
: None val
```
#### Parameters

*   keepalive: [Bool](builtin-Bool) val
*   conn: [TCPConnection](net-TCPConnection) tag

#### Returns

* [None](builtin-None) val

---

### _write_headers

Write all of the HTTP headers to the comm link.


```pony
fun box _write_headers(
  conn: TCPConnection tag)
: None val
```
#### Parameters

*   conn: [TCPConnection](net-TCPConnection) tag

#### Returns

* [None](builtin-None) val

---

