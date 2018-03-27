# CommonLog

Logs HTTP requests in the common log format.


```pony
class ref CommonLog is
  Logger val
```

#### Implements

* [Logger](net-http-Logger) val

---

## Constructors

### create

```pony
new val create(
  out: OutStream tag)
: CommonLog val^
```
#### Parameters

*   out: [OutStream](builtin-OutStream) tag

#### Returns

* [CommonLog](net-http-CommonLog) val^

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

## Private Functions

### _entry

```pony
fun box _entry(
  s: String val)
: String val
```
#### Parameters

*   s: [String](builtin-String) val

#### Returns

* [String](builtin-String) val

---

