# _SessionGuard

Enforces the rule that an 'unsafe' request monopolizes the
HTTPSession. A 'safe' request does not modify a resource state on
the server, and such a request has no body.


```pony
class ref _SessionGuard
```

## Constructors

### create

```pony
new iso create(
  session: HTTPSession tag)
: _SessionGuard iso^
```
#### Parameters

*   session: [HTTPSession](net-http-HTTPSession) tag

#### Returns

* [_SessionGuard](net-http-_SessionGuard) iso^

---

## Public fields

* var current: ([Payload](net-http-Payload) val | [None](builtin-None) val)

---

## Public Functions

### submit

Accept a request for transmission to the server. This will fail if
the request is not "safe" and the HTTPSession is busy. Due to the
possibly large body size, these requests can not be queued.


```pony
fun ref submit(
  request: Payload val)
: None val ?
```
#### Parameters

*   request: [Payload](net-http-Payload) val

#### Returns

* [None](builtin-None) val ?

---

