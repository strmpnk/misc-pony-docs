# Range\[optional A: ([Real](builtin-Real)\[A\] val & ([I8](builtin-I8) val | [I16](builtin-I16) val | [I32](builtin-I32) val | [I64](builtin-I64) val | [I128](builtin-I128) val | [ILong](builtin-ILong) val | [ISize](builtin-ISize) val | [U8](builtin-U8) val | [U16](builtin-U16) val | [U32](builtin-U32) val | [U64](builtin-U64) val | [U128](builtin-U128) val | [ULong](builtin-ULong) val | [USize](builtin-USize) val | [F32](builtin-F32) val | [F64](builtin-F64) val))\]

Produces `[min, max)` with a step of `inc` for any `Number` type.

```pony
// iterating with for-loop
for i in Range(0, 10) do
  env.out.print(i.string())
end

// iterating over Range of U8 with while-loop
let range = Range[U8](5, 100, 5)
while range.has_next() do
  handle_u8(range.next())
end
```

Supports `min` being smaller than `max` with negative `inc`
but only for signed integer types and floats:

```pony
var previous = 11
for left in Range[I64](10, -5, -1) do
  if not (left < previous) then
    error
  end
  previous = left
end
```

If the `step` is not moving `min` towards `max` or if it is `0`,
the Range is considered infinite and iterating over it
will never terminate:

```pony
let infinite_range1 = Range(0, 1, 0)
infinite_range1.is_infinite() == true

let infinite_range2 = Range[I8](0, 10, -1)
for _ in infinite_range2 do
  env.out.print("will this ever end?")
  env.err.print("no, never!")
end
```

When using `Range` with  floating point types (`F32` and `F64`)
`inc` steps < 1.0 are possible. If any of the arguments contains
`NaN`, `+Inf` or `-Inf` the range is considered infinite as operations on
any of them won't move `min` towards `max`.
The actual values produced by such a `Range` are determined by what IEEE 754
defines as the result of `min` + `inc`:

```pony
for and_a_half in Range[F64](0.5, 100) do
  handle_half(and_a_half)
end

// this Range will produce 0 at first, then infinitely NaN
let nan: F64 = F64(0) / F64(0)
for what_am_i in Range[F64](0, 1000, nan) do
  wild_guess(what_am_i)
end
```



```pony
class ref Range[optional A: (Real[A] val & (I8 val | I16 val | I32 val | 
    I64 val | I128 val | ILong val | 
    ISize val | U8 val | U16 val | 
    U32 val | U64 val | U128 val | 
    ULong val | USize val | F32 val | 
    F64 val))] is
  Iterator[A] ref
```

#### Implements

* [Iterator](builtin-Iterator)\[A\] ref

---

## Constructors

### create

```pony
new ref create(
  min: A,
  max: A,
  inc: A = seq)
: Range[A] ref^
```
#### Parameters

*   min: A
*   max: A
*   inc: A = seq

#### Returns

* [Range](collections-Range)\[A\] ref^

---

## Public Functions

### has_next

```pony
fun box has_next()
: Bool val
```

#### Returns

* [Bool](builtin-Bool) val

---

### next

```pony
fun ref next()
: A
```

#### Returns

* A

---

### rewind

```pony
fun ref rewind()
: None val
```

#### Returns

* [None](builtin-None) val

---

### is_infinite

```pony
fun box is_infinite()
: Bool val
```

#### Returns

* [Bool](builtin-Bool) val

---

