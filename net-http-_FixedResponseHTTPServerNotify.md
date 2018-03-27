# _FixedResponseHTTPServerNotify

Test http server that spits out fixed responses.
apply returns a TCPListenNotify object.


```pony
primitive val _FixedResponseHTTPServerNotify
```

## Constructors

### create

```pony
new val create()
: _FixedResponseHTTPServerNotify val^
```

#### Returns

* [_FixedResponseHTTPServerNotify](net-http-_FixedResponseHTTPServerNotify) val^

---

## Public Functions

### apply

```pony
fun box apply(
  h': TestHelper val,
  f: {(String val)} iso,
  r: Array[String val] val)
: TCPListenNotify iso^
```
#### Parameters

*   h': [TestHelper](ponytest-TestHelper) val
*   f: {(String val)} iso
*   r: [Array](builtin-Array)\[[String](builtin-String) val\] val

#### Returns

* [TCPListenNotify](net-TCPListenNotify) iso^

---

### eq

```pony
fun box eq(
  that: _FixedResponseHTTPServerNotify val)
: Bool val
```
#### Parameters

*   that: [_FixedResponseHTTPServerNotify](net-http-_FixedResponseHTTPServerNotify) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: _FixedResponseHTTPServerNotify val)
: Bool val
```
#### Parameters

*   that: [_FixedResponseHTTPServerNotify](net-http-_FixedResponseHTTPServerNotify) val

#### Returns

* [Bool](builtin-Bool) val

---

