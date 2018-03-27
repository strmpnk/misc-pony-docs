# SSLContext

An SSL context is used to create SSL sessions.


```pony
class val SSLContext
```

## Constructors

### create

```pony
new ref create()
: SSLContext ref^
```

#### Returns

* [SSLContext](net-ssl-SSLContext) ref^

---

## Public Functions

### client

Create a client-side SSL session. If a hostname is supplied, the server
side certificate must be valid for that hostname.


```pony
fun box client(
  hostname: String val = seq)
: SSL iso^ ?
```
#### Parameters

*   hostname: [String](builtin-String) val = seq

#### Returns

* [SSL](net-ssl-SSL) iso^ ?

---

### server

Create a server-side SSL session.


```pony
fun box server()
: SSL iso^ ?
```

#### Returns

* [SSL](net-ssl-SSL) iso^ ?

---

### set_cert

The cert file is a PEM certificate chain. The key file is a private key.
Servers must set this. For clients, it is optional.


```pony
fun ref set_cert(
  cert: FilePath val,
  key: FilePath val)
: None val ?
```
#### Parameters

*   cert: [FilePath](files-FilePath) val
*   key: [FilePath](files-FilePath) val

#### Returns

* [None](builtin-None) val ?

---

### set_authority

Use a PEM file and/or a directory of PEM files to specify certificate
authorities. Clients must set this. For servers, it is optional. Use None
to indicate no file or no path. Raises an error if these verify locations
aren't valid, or if both are None.


```pony
fun ref set_authority(
  file: (FilePath val | None val),
  path: (FilePath val | None val) = seq)
: None val ?
```
#### Parameters

*   file: ([FilePath](files-FilePath) val | [None](builtin-None) val)
*   path: ([FilePath](files-FilePath) val | [None](builtin-None) val) = seq

#### Returns

* [None](builtin-None) val ?

---

### set_ciphers

Set the accepted ciphers. This replaces the existing list. Raises an error
if the cipher list is invalid.


```pony
fun ref set_ciphers(
  ciphers: String val)
: None val ?
```
#### Parameters

*   ciphers: [String](builtin-String) val

#### Returns

* [None](builtin-None) val ?

---

### set_client_verify

Set to true to require verification. Defaults to true.


```pony
fun ref set_client_verify(
  state: Bool val)
: None val
```
#### Parameters

*   state: [Bool](builtin-Bool) val

#### Returns

* [None](builtin-None) val

---

### set_server_verify

Set to true to require verification. Defaults to false.


```pony
fun ref set_server_verify(
  state: Bool val)
: None val
```
#### Parameters

*   state: [Bool](builtin-Bool) val

#### Returns

* [None](builtin-None) val

---

### set_verify_depth

Set the verify depth. Defaults to 6.


```pony
fun ref set_verify_depth(
  depth: U32 val)
: None val
```
#### Parameters

*   depth: [U32](builtin-U32) val

#### Returns

* [None](builtin-None) val

---

### allow_tls_v1

Allow TLS v1. Defaults to false.


```pony
fun ref allow_tls_v1(
  state: Bool val)
: None val
```
#### Parameters

*   state: [Bool](builtin-Bool) val

#### Returns

* [None](builtin-None) val

---

### allow_tls_v1_1

Allow TLS v1.1. Defaults to false.


```pony
fun ref allow_tls_v1_1(
  state: Bool val)
: None val
```
#### Parameters

*   state: [Bool](builtin-Bool) val

#### Returns

* [None](builtin-None) val

---

### allow_tls_v1_2

Allow TLS v1.2. Defaults to true.


```pony
fun ref allow_tls_v1_2(
  state: Bool val)
: None val
```
#### Parameters

*   state: [Bool](builtin-Bool) val

#### Returns

* [None](builtin-None) val

---

### dispose

Free the SSL context.


```pony
fun ref dispose()
: None val
```

#### Returns

* [None](builtin-None) val

---

## Private Functions

### _final

Free the SSL context.


```pony
fun box _final()
: None val
```

#### Returns

* [None](builtin-None) val

---

