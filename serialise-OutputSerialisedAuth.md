# OutputSerialisedAuth

This is a capability token that allows the holder to examine serialised data.
This should only be provided to types that need to write serialised data to
some output stream, such as a file or socket. A type with the SerialiseAuth
capability should usually not also have OutputSerialisedAuth, as the
combination gives the holder the ability to examine the bitwise contents of
any object it has a reference to.


```pony
primitive val OutputSerialisedAuth
```

## Constructors

### create

```pony
new val create(
  auth: AmbientAuth val)
: OutputSerialisedAuth val^
```
#### Parameters

*   auth: [AmbientAuth](builtin-AmbientAuth) val

#### Returns

* [OutputSerialisedAuth](serialise-OutputSerialisedAuth) val^

---

## Public Functions

### eq

```pony
fun box eq(
  that: OutputSerialisedAuth val)
: Bool val
```
#### Parameters

*   that: [OutputSerialisedAuth](serialise-OutputSerialisedAuth) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: OutputSerialisedAuth val)
: Bool val
```
#### Parameters

*   that: [OutputSerialisedAuth](serialise-OutputSerialisedAuth) val

#### Returns

* [Bool](builtin-Bool) val

---

