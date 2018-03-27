# _FormatFloat

Worker type providing to string conversions for floats.


```pony
primitive val _FormatFloat
```

## Constructors

### create

```pony
new val create()
: _FormatFloat val^
```

#### Returns

* [_FormatFloat](format-_FormatFloat) val^

---

## Public Functions

### f64

```pony
fun box f64(
  x: F64 val,
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

*   x: [F64](builtin-F64) val
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
  that: _FormatFloat val)
: Bool val
```
#### Parameters

*   that: [_FormatFloat](format-_FormatFloat) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: _FormatFloat val)
: Bool val
```
#### Parameters

*   that: [_FormatFloat](format-_FormatFloat) val

#### Returns

* [Bool](builtin-Bool) val

---

