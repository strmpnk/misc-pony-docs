# Serialise

```pony
primitive val Serialise
```

## Constructors

### create

```pony
new val create()
: Serialise val^
```

#### Returns

* [Serialise](serialise-Serialise) val^

---

## Public Functions

### signature

Returns a byte array that is unique to this compiled Pony binary, for the
purposes of comparing before deserialising any data from that source.
It is statistically impossible for two serialisation-incompatible Pony
binaries to have the same serialise signature.


```pony
fun box signature()
: Array[U8 val] val
```

#### Returns

* [Array](builtin-Array)\[[U8](builtin-U8) val\] val

---

### eq

```pony
fun box eq(
  that: Serialise val)
: Bool val
```
#### Parameters

*   that: [Serialise](serialise-Serialise) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: Serialise val)
: Bool val
```
#### Parameters

*   that: [Serialise](serialise-Serialise) val

#### Returns

* [Bool](builtin-Bool) val

---

