# Serialised

This represents serialised data. How it can be used depends on the other
capabilities a caller holds.


```pony
class val Serialised
```

## Constructors

### create

A caller with SerialiseAuth can create serialised data from any object.


```pony
new ref create(
  auth: SerialiseAuth val,
  data: Any box)
: Serialised ref^ ?
```
#### Parameters

*   auth: [SerialiseAuth](serialise-SerialiseAuth) val
*   data: [Any](builtin-Any) box

#### Returns

* [Serialised](serialise-Serialised) ref^ ?

---

### input

A caller with InputSerialisedAuth can create serialised data from any
arbitrary set of bytes. It is the caller's responsibility to ensure that
the data is in fact well-formed serialised data. This is currently the most
dangerous method, as there is currently no way to check validity at
runtime.


```pony
new ref input(
  auth: InputSerialisedAuth val,
  data: Array[U8 val] val)
: Serialised ref^
```
#### Parameters

*   auth: [InputSerialisedAuth](serialise-InputSerialisedAuth) val
*   data: [Array](builtin-Array)\[[U8](builtin-U8) val\] val

#### Returns

* [Serialised](serialise-Serialised) ref^

---

## Public Functions

### apply

A caller with DeserialiseAuth can create an object graph from serialised
data.


```pony
fun box apply(
  auth: DeserialiseAuth val)
: Any iso^ ?
```
#### Parameters

*   auth: [DeserialiseAuth](serialise-DeserialiseAuth) val

#### Returns

* [Any](builtin-Any) iso^ ?

---

### output

A caller with OutputSerialisedAuth can gain access to the underlying bytes
that contain the serialised data. This can be used to write those bytes to,
for example, a file or socket.


```pony
fun box output(
  auth: OutputSerialisedAuth val)
: Array[U8 val] val
```
#### Parameters

*   auth: [OutputSerialisedAuth](serialise-OutputSerialisedAuth) val

#### Returns

* [Array](builtin-Array)\[[U8](builtin-U8) val\] val

---

