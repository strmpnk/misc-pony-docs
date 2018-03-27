# SSL

An SSL session manages handshakes, encryption and decryption. It is not tied
to any transport layer.


```pony
class ref SSL
```

## Constructors

### _create

```pony
new ref _create(
  ctx: Pointer[_SSLContext val] tag,
  server: Bool val,
  verify: Bool val,
  hostname: String val = seq)
: SSL ref^ ?
```
#### Parameters

*   ctx: [Pointer](builtin-Pointer)\[[_SSLContext](net-ssl-_SSLContext) val\] tag
*   server: [Bool](builtin-Bool) val
*   verify: [Bool](builtin-Bool) val
*   hostname: [String](builtin-String) val = seq

#### Returns

* [SSL](net-ssl-SSL) ref^ ?

---

## Public Functions

### state

Returns the SSL session state.


```pony
fun box state()
: (SSLHandshake val | SSLAuthFail val | SSLReady val | 
    SSLError val)
```

#### Returns

* ([SSLHandshake](net-ssl-SSLHandshake) val | [SSLAuthFail](net-ssl-SSLAuthFail) val | [SSLReady](net-ssl-SSLReady) val | 
    [SSLError](net-ssl-SSLError) val)

---

### read

Returns unencrypted bytes to be passed to the application. If `expect` is
non-zero, the number of bytes returned will be exactly `expect`. If no data
(or less than `expect` bytes) is available, this returns None.


```pony
fun ref read(
  expect: USize val = seq)
: (Array[U8 val] iso^ | None val)
```
#### Parameters

*   expect: [USize](builtin-USize) val = seq

#### Returns

* ([Array](builtin-Array)\[[U8](builtin-U8) val\] iso^ | [None](builtin-None) val)

---

### write

When application data is sent, add it to the SSL session. Raises an error
if the handshake is not complete.


```pony
fun ref write(
  data: (String val | Array[U8 val] val))
: None val ?
```
#### Parameters

*   data: ([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)

#### Returns

* [None](builtin-None) val ?

---

### receive

When data is received, add it to the SSL session.


```pony
fun ref receive(
  data: (String val | Array[U8 val] val))
: None val
```
#### Parameters

*   data: ([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)

#### Returns

* [None](builtin-None) val

---

### can_send

Returns true if there are encrypted bytes to be passed to the destination.


```pony
fun ref can_send()
: Bool val
```

#### Returns

* [Bool](builtin-Bool) val

---

### send

Returns encrypted bytes to be passed to the destination. Raises an error
if no data is available.


```pony
fun ref send()
: Array[U8 val] iso^ ?
```

#### Returns

* [Array](builtin-Array)\[[U8](builtin-U8) val\] iso^ ?

---

### dispose

Dispose of the session.


```pony
fun ref dispose()
: None val
```

#### Returns

* [None](builtin-None) val

---

## Private Functions

### _final

Dispose of the session.


```pony
fun box _final()
: None val
```

#### Returns

* [None](builtin-None) val

---

### _verify_hostname

Verify that the certificate is valid for the given hostname.


```pony
fun ref _verify_hostname()
: None val
```

#### Returns

* [None](builtin-None) val

---

