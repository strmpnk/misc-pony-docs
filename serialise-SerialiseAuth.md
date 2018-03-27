# SerialiseAuth

This is a capability that allows the holder to serialise objects. It does not
allow the holder to examine serialised data or to deserialise objects.


```pony
primitive val SerialiseAuth
```

## Constructors

### create

```pony
new val create(
  auth: AmbientAuth val)
: SerialiseAuth val^
```
#### Parameters

*   auth: [AmbientAuth](builtin-AmbientAuth) val

#### Returns

* [SerialiseAuth](serialise-SerialiseAuth) val^

---

## Public Functions

### eq

```pony
fun box eq(
  that: SerialiseAuth val)
: Bool val
```
#### Parameters

*   that: [SerialiseAuth](serialise-SerialiseAuth) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: SerialiseAuth val)
: Bool val
```
#### Parameters

*   that: [SerialiseAuth](serialise-SerialiseAuth) val

#### Returns

* [Bool](builtin-Bool) val

---

