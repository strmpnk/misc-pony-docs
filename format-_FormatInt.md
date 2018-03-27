# _FormatInt

Worker type providing to string conversions for integers.


```pony
primitive val _FormatInt
```

## Constructors

### create

```pony
new val create()
: _FormatInt val^
```

#### Returns

* [_FormatInt](format-_FormatInt) val^

---

## Public Functions

### u8

```pony
fun box u8(
  x: U8 val,
  neg: Bool val,
  fmt: (FormatDefault val | FormatUTF32 val | FormatBinary val | 
    FormatBinaryBare val | FormatOctal val | FormatOctalBare val | 
    FormatHex val | FormatHexBare val | FormatHexSmall val | 
    FormatHexSmallBare val),
  prefix: (PrefixDefault val | PrefixSpace val | PrefixSign val),
  prec: USize val,
  width: USize val,
  align: (AlignLeft val | AlignRight val | AlignCenter val),
  fill: U32 val)
: String iso^
```
#### Parameters

*   x: [U8](builtin-U8) val
*   neg: [Bool](builtin-Bool) val
*   fmt: ([FormatDefault](format-FormatDefault) val | [FormatUTF32](format-FormatUTF32) val | [FormatBinary](format-FormatBinary) val | 
    [FormatBinaryBare](format-FormatBinaryBare) val | [FormatOctal](format-FormatOctal) val | [FormatOctalBare](format-FormatOctalBare) val | 
    [FormatHex](format-FormatHex) val | [FormatHexBare](format-FormatHexBare) val | [FormatHexSmall](format-FormatHexSmall) val | 
    [FormatHexSmallBare](format-FormatHexSmallBare) val)
*   prefix: ([PrefixDefault](format-PrefixDefault) val | [PrefixSpace](format-PrefixSpace) val | [PrefixSign](format-PrefixSign) val)
*   prec: [USize](builtin-USize) val
*   width: [USize](builtin-USize) val
*   align: ([AlignLeft](format-AlignLeft) val | [AlignRight](format-AlignRight) val | [AlignCenter](format-AlignCenter) val)
*   fill: [U32](builtin-U32) val

#### Returns

* [String](builtin-String) iso^

---

### u16

```pony
fun box u16(
  x: U16 val,
  neg: Bool val,
  fmt: (FormatDefault val | FormatUTF32 val | FormatBinary val | 
    FormatBinaryBare val | FormatOctal val | FormatOctalBare val | 
    FormatHex val | FormatHexBare val | FormatHexSmall val | 
    FormatHexSmallBare val),
  prefix: (PrefixDefault val | PrefixSpace val | PrefixSign val),
  prec: USize val,
  width: USize val,
  align: (AlignLeft val | AlignRight val | AlignCenter val),
  fill: U32 val)
: String iso^
```
#### Parameters

*   x: [U16](builtin-U16) val
*   neg: [Bool](builtin-Bool) val
*   fmt: ([FormatDefault](format-FormatDefault) val | [FormatUTF32](format-FormatUTF32) val | [FormatBinary](format-FormatBinary) val | 
    [FormatBinaryBare](format-FormatBinaryBare) val | [FormatOctal](format-FormatOctal) val | [FormatOctalBare](format-FormatOctalBare) val | 
    [FormatHex](format-FormatHex) val | [FormatHexBare](format-FormatHexBare) val | [FormatHexSmall](format-FormatHexSmall) val | 
    [FormatHexSmallBare](format-FormatHexSmallBare) val)
*   prefix: ([PrefixDefault](format-PrefixDefault) val | [PrefixSpace](format-PrefixSpace) val | [PrefixSign](format-PrefixSign) val)
*   prec: [USize](builtin-USize) val
*   width: [USize](builtin-USize) val
*   align: ([AlignLeft](format-AlignLeft) val | [AlignRight](format-AlignRight) val | [AlignCenter](format-AlignCenter) val)
*   fill: [U32](builtin-U32) val

#### Returns

* [String](builtin-String) iso^

---

### u32

```pony
fun box u32(
  x: U32 val,
  neg: Bool val,
  fmt: (FormatDefault val | FormatUTF32 val | FormatBinary val | 
    FormatBinaryBare val | FormatOctal val | FormatOctalBare val | 
    FormatHex val | FormatHexBare val | FormatHexSmall val | 
    FormatHexSmallBare val),
  prefix: (PrefixDefault val | PrefixSpace val | PrefixSign val),
  prec: USize val,
  width: USize val,
  align: (AlignLeft val | AlignRight val | AlignCenter val),
  fill: U32 val)
: String iso^
```
#### Parameters

*   x: [U32](builtin-U32) val
*   neg: [Bool](builtin-Bool) val
*   fmt: ([FormatDefault](format-FormatDefault) val | [FormatUTF32](format-FormatUTF32) val | [FormatBinary](format-FormatBinary) val | 
    [FormatBinaryBare](format-FormatBinaryBare) val | [FormatOctal](format-FormatOctal) val | [FormatOctalBare](format-FormatOctalBare) val | 
    [FormatHex](format-FormatHex) val | [FormatHexBare](format-FormatHexBare) val | [FormatHexSmall](format-FormatHexSmall) val | 
    [FormatHexSmallBare](format-FormatHexSmallBare) val)
*   prefix: ([PrefixDefault](format-PrefixDefault) val | [PrefixSpace](format-PrefixSpace) val | [PrefixSign](format-PrefixSign) val)
*   prec: [USize](builtin-USize) val
*   width: [USize](builtin-USize) val
*   align: ([AlignLeft](format-AlignLeft) val | [AlignRight](format-AlignRight) val | [AlignCenter](format-AlignCenter) val)
*   fill: [U32](builtin-U32) val

#### Returns

* [String](builtin-String) iso^

---

### u64

```pony
fun box u64(
  x: U64 val,
  neg: Bool val,
  fmt: (FormatDefault val | FormatUTF32 val | FormatBinary val | 
    FormatBinaryBare val | FormatOctal val | FormatOctalBare val | 
    FormatHex val | FormatHexBare val | FormatHexSmall val | 
    FormatHexSmallBare val),
  prefix: (PrefixDefault val | PrefixSpace val | PrefixSign val),
  prec: USize val,
  width: USize val,
  align: (AlignLeft val | AlignRight val | AlignCenter val),
  fill: U32 val)
: String iso^
```
#### Parameters

*   x: [U64](builtin-U64) val
*   neg: [Bool](builtin-Bool) val
*   fmt: ([FormatDefault](format-FormatDefault) val | [FormatUTF32](format-FormatUTF32) val | [FormatBinary](format-FormatBinary) val | 
    [FormatBinaryBare](format-FormatBinaryBare) val | [FormatOctal](format-FormatOctal) val | [FormatOctalBare](format-FormatOctalBare) val | 
    [FormatHex](format-FormatHex) val | [FormatHexBare](format-FormatHexBare) val | [FormatHexSmall](format-FormatHexSmall) val | 
    [FormatHexSmallBare](format-FormatHexSmallBare) val)
*   prefix: ([PrefixDefault](format-PrefixDefault) val | [PrefixSpace](format-PrefixSpace) val | [PrefixSign](format-PrefixSign) val)
*   prec: [USize](builtin-USize) val
*   width: [USize](builtin-USize) val
*   align: ([AlignLeft](format-AlignLeft) val | [AlignRight](format-AlignRight) val | [AlignCenter](format-AlignCenter) val)
*   fill: [U32](builtin-U32) val

#### Returns

* [String](builtin-String) iso^

---

### u128

```pony
fun box u128(
  x: U128 val,
  neg: Bool val,
  fmt: (FormatDefault val | FormatUTF32 val | FormatBinary val | 
    FormatBinaryBare val | FormatOctal val | FormatOctalBare val | 
    FormatHex val | FormatHexBare val | FormatHexSmall val | 
    FormatHexSmallBare val) = seq,
  prefix: (PrefixDefault val | PrefixSpace val | PrefixSign val) = seq,
  prec: USize val = seq,
  width: USize val = seq,
  align: (AlignLeft val | AlignRight val | AlignCenter val) = seq,
  fill: U32 val = seq)
: String iso^
```
#### Parameters

*   x: [U128](builtin-U128) val
*   neg: [Bool](builtin-Bool) val
*   fmt: ([FormatDefault](format-FormatDefault) val | [FormatUTF32](format-FormatUTF32) val | [FormatBinary](format-FormatBinary) val | 
    [FormatBinaryBare](format-FormatBinaryBare) val | [FormatOctal](format-FormatOctal) val | [FormatOctalBare](format-FormatOctalBare) val | 
    [FormatHex](format-FormatHex) val | [FormatHexBare](format-FormatHexBare) val | [FormatHexSmall](format-FormatHexSmall) val | 
    [FormatHexSmallBare](format-FormatHexSmallBare) val) = seq
*   prefix: ([PrefixDefault](format-PrefixDefault) val | [PrefixSpace](format-PrefixSpace) val | [PrefixSign](format-PrefixSign) val) = seq
*   prec: [USize](builtin-USize) val = seq
*   width: [USize](builtin-USize) val = seq
*   align: ([AlignLeft](format-AlignLeft) val | [AlignRight](format-AlignRight) val | [AlignCenter](format-AlignCenter) val) = seq
*   fill: [U32](builtin-U32) val = seq

#### Returns

* [String](builtin-String) iso^

---

### eq

```pony
fun box eq(
  that: _FormatInt val)
: Bool val
```
#### Parameters

*   that: [_FormatInt](format-_FormatInt) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: _FormatInt val)
: Bool val
```
#### Parameters

*   that: [_FormatInt](format-_FormatInt) val

#### Returns

* [Bool](builtin-Bool) val

---

## Private Functions

### _large

```pony
fun box _large()
: String val
```

#### Returns

* [String](builtin-String) val

---

### _small

```pony
fun box _small()
: String val
```

#### Returns

* [String](builtin-String) val

---

### _fmt_int

```pony
fun box _fmt_int(
  fmt: (FormatDefault val | FormatUTF32 val | FormatBinary val | 
    FormatBinaryBare val | FormatOctal val | FormatOctalBare val | 
    FormatHex val | FormatHexBare val | FormatHexSmall val | 
    FormatHexSmallBare val))
: (U32 val , String val , String val)
```
#### Parameters

*   fmt: ([FormatDefault](format-FormatDefault) val | [FormatUTF32](format-FormatUTF32) val | [FormatBinary](format-FormatBinary) val | 
    [FormatBinaryBare](format-FormatBinaryBare) val | [FormatOctal](format-FormatOctal) val | [FormatOctalBare](format-FormatOctalBare) val | 
    [FormatHex](format-FormatHex) val | [FormatHexBare](format-FormatHexBare) val | [FormatHexSmall](format-FormatHexSmall) val | 
    [FormatHexSmallBare](format-FormatHexSmallBare) val)

#### Returns

* ([U32](builtin-U32) val , [String](builtin-String) val , [String](builtin-String) val)

---

### _prefix

```pony
fun box _prefix(
  neg: Bool val,
  prefix: (PrefixDefault val | PrefixSpace val | PrefixSign val))
: String val
```
#### Parameters

*   neg: [Bool](builtin-Bool) val
*   prefix: ([PrefixDefault](format-PrefixDefault) val | [PrefixSpace](format-PrefixSpace) val | [PrefixSign](format-PrefixSign) val)

#### Returns

* [String](builtin-String) val

---

### _extend_digits

```pony
fun box _extend_digits(
  s: String ref,
  digits: USize val)
: None val
```
#### Parameters

*   s: [String](builtin-String) ref
*   digits: [USize](builtin-USize) val

#### Returns

* [None](builtin-None) val

---

### _pad

```pony
fun box _pad(
  s: String ref,
  width: USize val,
  align: (AlignLeft val | AlignRight val | AlignCenter val),
  fill: U32 val)
: None val
```
#### Parameters

*   s: [String](builtin-String) ref
*   width: [USize](builtin-USize) val
*   align: ([AlignLeft](format-AlignLeft) val | [AlignRight](format-AlignRight) val | [AlignCenter](format-AlignCenter) val)
*   fill: [U32](builtin-U32) val

#### Returns

* [None](builtin-None) val

---

