# JoiningListenNotifier

The sole purpose of this listener is to keep a joining worker process alive
while waiting to get cluster info and initialize.
TODO: Eliminate the need for this.


```pony
class iso JoiningListenNotifier is
  TCPListenNotify ref
```

#### Implements

* [TCPListenNotify](net-TCPListenNotify) ref

---

## Constructors

### create

```pony
new iso create()
: JoiningListenNotifier iso^
```

#### Returns

* [JoiningListenNotifier](wallaroo-ent-network-JoiningListenNotifier) iso^

---

## Public Functions

### listening

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

### connected

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

### closed

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

