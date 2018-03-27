# TCPListenNotify

Notifications for TCP listeners.

For an example of using this class, please see the documentation for the
`TCPListener` actor.


```pony
interface ref TCPListenNotify
```

## Public Functions

### listening

Called when the listener has been bound to an address.


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

Called if it wasn't possible to bind the listener to an address.

It is expected to implement proper error handling. You need to opt in to
ignoring errors, which can be implemented like this:

```pony
fun ref not_listening(listen: TCPListener ref) =>
  None
```


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

Called when the listener is closed.


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

Create a new TCPConnectionNotify to attach to a new TCPConnection for a
newly established connection to the server.


```pony
fun ref connected(
  listen: TCPListener ref)
: TCPConnectionNotify iso^ ?
```
#### Parameters

*   listen: [TCPListener](net-TCPListener) ref

#### Returns

* [TCPConnectionNotify](net-TCPConnectionNotify) iso^ ?

---

