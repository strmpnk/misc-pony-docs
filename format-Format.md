# Format

Provides functions for generating formatted strings.

* fmt. Format to use.
* prefix. Prefix to use.
* prec. Precision to use. The exact meaning of this depends on the type,
but is generally the number of characters used for all, or part, of the
string. A value of -1 indicates that the default for the type should be
used.
* width. The minimum number of characters that will be in the produced
string. If necessary the string will be padded with the fill character to
make it long enough.
*align. Specify whether fill characters should be added at the beginning or
end of the generated string, or both.
*fill: The character to pad a string with if is is shorter than width.


```pony
primitive val Format
```

## Constructors

### create

```pony
new val create()
: Format val^
```

#### Returns

* [Format](format-Format) val^

---

## Public Functions

### apply

```pony
fun box apply(
  str: String val,
  fmt: FormatDefault val = seq,
  prefix: PrefixDefault val = seq,
  prec: USize val = seq,
  width: USize val = seq,
  align: (AlignLeft val | AlignRight val | AlignCenter val) = seq,
  fill: U32 val = seq)
: String iso^
```
#### Parameters

*   str: [String](builtin-String) val
*   fmt: [FormatDefault](format-FormatDefault) val = seq
*   prefix: [PrefixDefault](format-PrefixDefault) val = seq
*   prec: [USize](builtin-USize) val = seq
*   width: [USize](builtin-USize) val = seq
*   align: ([AlignLeft](format-AlignLeft) val | [AlignRight](format-AlignRight) val | [AlignCenter](format-AlignCenter) val) = seq
*   fill: [U32](builtin-U32) val = seq

#### Returns

* [String](builtin-String) iso^

---

### int\[A: (([I8](builtin-I8) val | [I16](builtin-I16) val | [I32](builtin-I32) val | [I64](builtin-I64) val | [I128](builtin-I128) val | [ILong](builtin-ILong) val | [ISize](builtin-ISize) val | [U8](builtin-U8) val | [U16](builtin-U16) val | [U32](builtin-U32) val | [U64](builtin-U64) val | [U128](builtin-U128) val | [ULong](builtin-ULong) val | [USize](builtin-USize) val) & [Integer](builtin-Integer)\[A\])\]

```pony
fun box int[A: ((I8 val | I16 val | I32 val | 
    I64 val | I128 val | ILong val | 
    ISize val | U8 val | U16 val | 
    U32 val | U64 val | U128 val | 
    ULong val | USize val) & Integer[A])](
  x: A,
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

*   x: A
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

### float\[A: (([F32](builtin-F32) val | [F64](builtin-F64) val) & [FloatingPoint](builtin-FloatingPoint)\[A\])\]

```pony
fun box float[A: ((F32 val | F64 val) & FloatingPoint[A])](
  x: A,
  fmt: (FormatDefault val | FormatExp val | FormatExpLarge val | 
    FormatFix val | FormatFixLarge val | FormatGeneral val | 
    FormatGeneralLarge val) = seq,
  prefix: (PrefixDefault val | PrefixSpace val | PrefixSign val) = seq,
  prec: USize val = seq,
  width: USize val = seq,
  align: (AlignLeft val | AlignRight val | AlignCenter val) = seq,
  fill: U32 val = seq)
: String iso^
```
#### Parameters

*   x: A
*   fmt: ([FormatDefault](format-FormatDefault) val | [FormatExp](format-FormatExp) val | [FormatExpLarge](format-FormatExpLarge) val | 
    [FormatFix](format-FormatFix) val | [FormatFixLarge](format-FormatFixLarge) val | [FormatGeneral](format-FormatGeneral) val | 
    [FormatGeneralLarge](format-FormatGeneralLarge) val) = seq
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
  that: Format val)
: Bool val
```
#### Parameters

*   that: [Format](format-Format) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: Format val)
: Bool val
```
#### Parameters

*   that: [Format](format-Format) val

#### Returns

* [Bool](builtin-Bool) val

---

