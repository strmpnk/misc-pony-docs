# InputSerialisedAuth

This is a capability token that allows the holder to treat data arbitrary
bytes as serialised data. This is the most dangerous capability, as currently
it is possible for a malformed chunk of data to crash your program if it is
deserialised.


```pony
primitive val InputSerialisedAuth
```

## Constructors

### create

```pony
new val create(
  auth: AmbientAuth val)
: InputSerialisedAuth val^
```
#### Parameters

*   auth: [AmbientAuth](builtin-AmbientAuth) val

#### Returns

* [InputSerialisedAuth](serialise-InputSerialisedAuth) val^

---

## Public Functions

### eq

```pony
fun box eq(
  that: InputSerialisedAuth val)
: Bool val
```
#### Parameters

*   that: [InputSerialisedAuth](serialise-InputSerialisedAuth) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: InputSerialisedAuth val)
: Bool val
```
#### Parameters

*   that: [InputSerialisedAuth](serialise-InputSerialisedAuth) val

#### Returns

* [Bool](builtin-Bool) val

---

