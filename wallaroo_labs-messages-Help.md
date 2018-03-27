# Help

```pony
primitive val Help
```

## Constructors

### create

```pony
new val create()
: Help val^
```

#### Returns

* [Help](wallaroo_labs-messages-Help) val^

---

## Public Functions

### flatten

```pony
fun val flatten(
  e1: Array[(String val | Array[U8 val] val)] val)
: Array[U8 val] val
```
#### Parameters

*   e1: [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val

#### Returns

* [Array](builtin-Array)\[[U8](builtin-U8) val\] val

---

### general

```pony
fun box general(
  h: TestHelper val,
  enc: (_EncoderFn0 ref | _EncoderFn1 ref),
  extr: _ExtractFn val)
: None val ?
```
#### Parameters

*   h: [TestHelper](ponytest-TestHelper) val
*   enc: ([_EncoderFn0](wallaroo_labs-messages-_EncoderFn0) ref | [_EncoderFn1](wallaroo_labs-messages-_EncoderFn1) ref)
*   extr: [_ExtractFn](wallaroo_labs-messages-_ExtractFn) val

#### Returns

* [None](builtin-None) val ?

---

### eq

```pony
fun box eq(
  that: Help val)
: Bool val
```
#### Parameters

*   that: [Help](wallaroo_labs-messages-Help) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: Help val)
: Bool val
```
#### Parameters

*   that: [Help](wallaroo_labs-messages-Help) val

#### Returns

* [Bool](builtin-Bool) val

---

