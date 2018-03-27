# ContentsLog

Logs the contents of HTTP requests and responses.


```pony
class ref ContentsLog is
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
: ContentsLog val^
```
#### Parameters

*   out: [OutStream](builtin-OutStream) tag

#### Returns

* [ContentsLog](net-http-ContentsLog) val^

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

