# DiscardLog

Doesn't log anything.


```pony
primitive val DiscardLog
```

## Constructors

### create

```pony
new val create()
: DiscardLog val^
```

#### Returns

* [DiscardLog](net-http-DiscardLog) val^

---

## Public Functions

### apply

```pony
fun val apply(
  ip: String val,
  body_size: USize val,
  request: Payload val,
  response: Payload val)
: None val
```
#### Parameters

*   ip: [String](builtin-String) val
*   body_size: [USize](builtin-USize) val
*   request: [Payload](net-http-Payload) val
*   response: [Payload](net-http-Payload) val

#### Returns

* [None](builtin-None) val

---

### eq

```pony
fun box eq(
  that: DiscardLog val)
: Bool val
```
#### Parameters

*   that: [DiscardLog](net-http-DiscardLog) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: DiscardLog val)
: Bool val
```
#### Parameters

*   that: [DiscardLog](net-http-DiscardLog) val

#### Returns

* [Bool](builtin-Bool) val

---

