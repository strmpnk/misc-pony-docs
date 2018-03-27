# _ServerListener

Manages the listening socket for an HTTP server. Incoming requests
are assembled and dispatched.


```pony
class ref _ServerListener is
  TCPListenNotify ref
```

#### Implements

* [TCPListenNotify](net-TCPListenNotify) ref

---

## Constructors

### create

Creates a new listening socket manager.


```pony
new iso create(
  server: HTTPServer tag,
  sslctx: (SSLContext val | None val),
  handler: HandlerFactory val,
  logger: Logger val,
  reversedns: (AmbientAuth val | NetAuth val | DNSAuth val | 
    None val))
: _ServerListener iso^
```
#### Parameters

*   server: [HTTPServer](net-http-HTTPServer) tag
*   sslctx: ([SSLContext](net-ssl-SSLContext) val | [None](builtin-None) val)
*   handler: [HandlerFactory](net-http-HandlerFactory) val
*   logger: [Logger](net-http-Logger) val
*   reversedns: ([AmbientAuth](builtin-AmbientAuth) val | [NetAuth](net-NetAuth) val | [DNSAuth](net-DNSAuth) val | 
    [None](builtin-None) val)

#### Returns

* [_ServerListener](net-http-_ServerListener) iso^

---

## Public Functions

### listening

Inform the server of the bound IP address.


```pony
fun ref listening(
  listen: TCPListener ref)
: None val
```
#### Parameters

*   listen: [TCPListener](net-TCPListener) ref

#### Returns

* [None](builtin-None) val

---

### not_listening

Inform the server we failed to listen.


```pony
fun ref not_listening(
  listen: TCPListener ref)
: None val
```
#### Parameters

*   listen: [TCPListener](net-TCPListener) ref

#### Returns

* [None](builtin-None) val

---

### closed

Inform the server we have stopped listening.


```pony
fun ref closed(
  listen: TCPListener ref)
: None val
```
#### Parameters

*   listen: [TCPListener](net-TCPListener) ref

#### Returns

* [None](builtin-None) val

---

### connected

Create a notifier for a specific HTTP socket. A new instance of the
back-end Handler is passed along so it can be used on each `Payload`.


```pony
fun ref connected(
  listen: TCPListener ref)
: TCPConnectionNotify iso^
```
#### Parameters

*   listen: [TCPListener](net-TCPListener) ref

#### Returns

* [TCPConnectionNotify](net-TCPConnectionNotify) iso^

---

