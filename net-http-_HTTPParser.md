# _HTTPParser

This is the HTTP parser that builds a message `Payload` object
representing either a Request or a Response from received chunks of data.


```pony
class ref _HTTPParser
```

## Constructors

### request

```pony
new ref request(
  session': HTTPSession tag)
: _HTTPParser ref^
```
#### Parameters

*   session': [HTTPSession](net-http-HTTPSession) tag

#### Returns

* [_HTTPParser](net-http-_HTTPParser) ref^

---

### response

```pony
new ref response(
  session': HTTPSession tag)
: _HTTPParser ref^
```
#### Parameters

*   session': [HTTPSession](net-http-HTTPSession) tag

#### Returns

* [_HTTPParser](net-http-_HTTPParser) ref^

---

## Public Functions

### parse

Analyze new data based on the parser's current internal state.


```pony
fun ref parse(
  buffer: Reader ref)
: None val ?
```
#### Parameters

*   buffer: [Reader](buffered-Reader) ref

#### Returns

* [None](builtin-None) val ?

---

### closed

The connection has closed, which may signal that all remaining data is the
payload body.


```pony
fun ref closed(
  buffer: Reader ref)
: None val
```
#### Parameters

*   buffer: [Reader](buffered-Reader) ref

#### Returns

* [None](builtin-None) val

---

## Private Functions

### _deliver

The parser is finished with the message headers so we can push it
to the `HTTPSession`. The body may come later.


```pony
fun ref _deliver()
: None val
```

#### Returns

* [None](builtin-None) val

---

### _restart

Restart parser state for the next message. It will be of the same
kind as the last one.


```pony
fun ref _restart()
: None val
```

#### Returns

* [None](builtin-None) val

---

### _parse_request

Look for "<Method> <URL> <Proto>", the first line of an HTTP
'request' message.


```pony
fun ref _parse_request(
  buffer: Reader ref)
: None val ?
```
#### Parameters

*   buffer: [Reader](buffered-Reader) ref

#### Returns

* [None](builtin-None) val ?

---

### _parse_response

Look for "<Proto> <Code> <Description>", the first line of an
HTTP 'response' message.


```pony
fun ref _parse_response(
  buffer: Reader ref)
: None val ?
```
#### Parameters

*   buffer: [Reader](buffered-Reader) ref

#### Returns

* [None](builtin-None) val ?

---

### _parse_headers

Look for: "<Key>:<Value>" or the empty line that marks the end of
all the headers.


```pony
fun ref _parse_headers(
  buffer: Reader ref)
: None val ?
```
#### Parameters

*   buffer: [Reader](buffered-Reader) ref

#### Returns

* [None](builtin-None) val ?

---

### _process_header

Save a header value. Raise an error on not finding the colon
or can't interpret the value.


```pony
fun ref _process_header(
  line: String val)
: None val ?
```
#### Parameters

*   line: [String](builtin-String) val

#### Returns

* [None](builtin-None) val ?

---

### _setauth

Fill in username and password from an authentication header.


```pony
fun ref _setauth(
  auth: String val)
: None val
```
#### Parameters

*   auth: [String](builtin-String) val

#### Returns

* [None](builtin-None) val

---

### _set_header_end

Line size is zero, so we have reached the end of the headers.
Certain status codes mean there is no body.


```pony
fun ref _set_header_end()
: None val
```

#### Returns

* [None](builtin-None) val

---

### _parse_content_length

Look for `_expected_length` bytes set by having seen a `Content-Length`
header. We may not see it all at once but we process the lesser of
what we need and what is available in the buffer.


```pony
fun ref _parse_content_length(
  buffer: Reader ref)
: None val
```
#### Parameters

*   buffer: [Reader](buffered-Reader) ref

#### Returns

* [None](builtin-None) val

---

### _parse_chunk_start

Look for the beginning of a chunk, which is a length in hex on a line
terminated by CRLF. An explicit length of zero marks the end of
the entire chunked message body.


```pony
fun ref _parse_chunk_start(
  buffer: Reader ref)
: None val ?
```
#### Parameters

*   buffer: [Reader](buffered-Reader) ref

#### Returns

* [None](builtin-None) val ?

---

### _parse_chunk

Look for a chunk of the size set by `_parse_chunk_start`. We may
not see it all at once but we process the lesser of what we need
and what is available in the buffer. ChunkedTransfer mode always
delivers directly to the HTTPSession handler.


```pony
fun ref _parse_chunk(
  buffer: Reader ref)
: None val
```
#### Parameters

*   buffer: [Reader](buffered-Reader) ref

#### Returns

* [None](builtin-None) val

---

### _parse_chunk_end

Look for the CRLF that ends every chunk. AFter that we look for
the next chunk, or that was the special ending chunk.


```pony
fun ref _parse_chunk_end(
  buffer: Reader ref)
: None val
```
#### Parameters

*   buffer: [Reader](buffered-Reader) ref

#### Returns

* [None](builtin-None) val

---

