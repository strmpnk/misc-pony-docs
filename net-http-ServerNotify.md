# ServerNotify

Notifications about the creation and closing of `TCPConnection`s
within HTTP servers.


```pony
interface ref ServerNotify
```

## Public Functions

### listening

Called when we are listening.


```pony
fun ref listening(
  server: HTTPServer ref)
: None val
```
#### Parameters

*   server: [HTTPServer](net-http-HTTPServer) ref

#### Returns

* [None](builtin-None) val

---

### not_listening

Called when we fail to listen.


```pony
fun ref not_listening(
  server: HTTPServer ref)
: None val
```
#### Parameters

*   server: [HTTPServer](net-http-HTTPServer) ref

#### Returns

* [None](builtin-None) val

---

### closed

Called when we stop listening.


```pony
fun ref closed(
  server: HTTPServer ref)
: None val
```
#### Parameters

*   server: [HTTPServer](net-http-HTTPServer) ref

#### Returns

* [None](builtin-None) val

---

