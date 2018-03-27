# Base64

```pony
primitive val Base64
```

## Constructors

### create

```pony
new val create()
: Base64 val^
```

#### Returns

* [Base64](encode-base64-Base64) val^

---

## Public Functions

### encode_pem

Encode for PEM (RFC 1421).


```pony
fun box encode_pem(
  data: ReadSeq[U8 val] box)
: String iso^
```
#### Parameters

*   data: [ReadSeq](builtin-ReadSeq)\[[U8](builtin-U8) val\] box

#### Returns

* [String](builtin-String) iso^

---

### encode_mime

Encode for MIME (RFC 2045).


```pony
fun box encode_mime(
  data: ReadSeq[U8 val] box)
: String iso^
```
#### Parameters

*   data: [ReadSeq](builtin-ReadSeq)\[[U8](builtin-U8) val\] box

#### Returns

* [String](builtin-String) iso^

---

### encode_url\[optional A: [Seq](builtin-Seq)\[[U8](builtin-U8) val\] iso\]

Encode for URLs (RFC 4648). Padding characters are stripped by default.


```pony
fun box encode_url[optional A: Seq[U8 val] iso](
  data: ReadSeq[U8 val] box,
  pad: Bool val = seq)
: A^
```
#### Parameters

*   data: [ReadSeq](builtin-ReadSeq)\[[U8](builtin-U8) val\] box
*   pad: [Bool](builtin-Bool) val = seq

#### Returns

* A^

---

### encode\[optional A: [Seq](builtin-Seq)\[[U8](builtin-U8) val\] iso\]

Configurable encoding. The defaults are for RFC 4648.


```pony
fun box encode[optional A: Seq[U8 val] iso](
  data: ReadSeq[U8 val] box,
  at62: U8 val = seq,
  at63: U8 val = seq,
  pad: U8 val = seq,
  linelen: USize val = seq,
  linesep: String val = seq)
: A^
```
#### Parameters

*   data: [ReadSeq](builtin-ReadSeq)\[[U8](builtin-U8) val\] box
*   at62: [U8](builtin-U8) val = seq
*   at63: [U8](builtin-U8) val = seq
*   pad: [U8](builtin-U8) val = seq
*   linelen: [USize](builtin-USize) val = seq
*   linesep: [String](builtin-String) val = seq

#### Returns

* A^

---

### decode_url\[optional A: [Seq](builtin-Seq)\[[U8](builtin-U8) val\] iso\]

Decode for URLs (RFC 4648).


```pony
fun box decode_url[optional A: Seq[U8 val] iso](
  data: ReadSeq[U8 val] box)
: A^ ?
```
#### Parameters

*   data: [ReadSeq](builtin-ReadSeq)\[[U8](builtin-U8) val\] box

#### Returns

* A^ ?

---

### decode\[optional A: [Seq](builtin-Seq)\[[U8](builtin-U8) val\] iso\]

Configurable decoding. The defaults are for RFC 4648. Missing padding is
not an error. Non-base64 data, other than whitespace (which can appear at
any time), is an error.


```pony
fun box decode[optional A: Seq[U8 val] iso](
  data: ReadSeq[U8 val] box,
  at62: U8 val = seq,
  at63: U8 val = seq,
  pad: U8 val = seq)
: A^ ?
```
#### Parameters

*   data: [ReadSeq](builtin-ReadSeq)\[[U8](builtin-U8) val\] box
*   at62: [U8](builtin-U8) val = seq
*   at63: [U8](builtin-U8) val = seq
*   pad: [U8](builtin-U8) val = seq

#### Returns

* A^ ?

---

### eq

```pony
fun box eq(
  that: Base64 val)
: Bool val
```
#### Parameters

*   that: [Base64](encode-base64-Base64) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: Base64 val)
: Bool val
```
#### Parameters

*   that: [Base64](encode-base64-Base64) val

#### Returns

* [Bool](builtin-Bool) val

---

## Private Functions

### _enc_byte

Encode a single byte.


```pony
fun box _enc_byte(
  i: U8 val,
  at62: U8 val,
  at63: U8 val)
: U8 val ?
```
#### Parameters

*   i: [U8](builtin-U8) val
*   at62: [U8](builtin-U8) val
*   at63: [U8](builtin-U8) val

#### Returns

* [U8](builtin-U8) val ?

---

