# Logger

Handles logging request/response pairs.


```pony
interface val Logger
```

## Public Functions

### apply

```pony
fun val apply(
  ip: String val,
  body_size: USize val,
  request: Payload val,
  response: Payload val)
: Any tag
```
#### Parameters

*   ip: [String](builtin-String) val
*   body_size: [USize](builtin-USize) val
*   request: [Payload](net-http-Payload) val
*   response: [Payload](net-http-Payload) val

#### Returns

* [Any](builtin-Any) tag

---

