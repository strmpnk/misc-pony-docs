# DeserialiseAuth

This is a capability token that allows the holder to deserialise objects. It
does not allow the holder to serialise objects or examine serialised.


```pony
primitive val DeserialiseAuth
```

## Constructors

### create

```pony
new val create(
  auth: AmbientAuth val)
: DeserialiseAuth val^
```
#### Parameters

*   auth: [AmbientAuth](builtin-AmbientAuth) val

#### Returns

* [DeserialiseAuth](serialise-DeserialiseAuth) val^

---

## Public Functions

### eq

```pony
fun box eq(
  that: DeserialiseAuth val)
: Bool val
```
#### Parameters

*   that: [DeserialiseAuth](serialise-DeserialiseAuth) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: DeserialiseAuth val)
: Bool val
```
#### Parameters

*   that: [DeserialiseAuth](serialise-DeserialiseAuth) val

#### Returns

* [Bool](builtin-Bool) val

---

