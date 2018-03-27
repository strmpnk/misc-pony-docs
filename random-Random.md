# Random

The `Random` trait should be implemented by all random number generators. The
only method you need to implement is `fun ref next(): 64`. Once that method
has been implemented, the `Random` trait provides default implementations of
conversions to other number types.


```pony
trait ref Random
```

## Constructors

### create

Create with the specified seed. Returned values are deterministic for a
given seed.


```pony
new ref create(
  x: U64 val = seq,
  y: U64 val = seq)
: Random ref^
```
#### Parameters

*   x: [U64](builtin-U64) val = seq
*   y: [U64](builtin-U64) val = seq

#### Returns

* [Random](random-Random) ref^

---

## Public Functions

### has_next

If used as an iterator, this always has another value.


```pony
fun tag has_next()
: Bool val
```

#### Returns

* [Bool](builtin-Bool) val

---

### next

A random integer in [0, 2^64)


```pony
fun ref next()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### u8

A random integer in [0, 2^8)


```pony
fun ref u8()
: U8 val
```

#### Returns

* [U8](builtin-U8) val

---

### u16

A random integer in [0, 2^16)


```pony
fun ref u16()
: U16 val
```

#### Returns

* [U16](builtin-U16) val

---

### u32

A random integer in [0, 2^32)


```pony
fun ref u32()
: U32 val
```

#### Returns

* [U32](builtin-U32) val

---

### u64

A random integer in [0, 2^64)


```pony
fun ref u64()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### u128

A random integer in [0, 2^128)


```pony
fun ref u128()
: U128 val
```

#### Returns

* [U128](builtin-U128) val

---

### ulong

A random integer in [0, ULong.max_value()]


```pony
fun ref ulong()
: ULong val
```

#### Returns

* [ULong](builtin-ULong) val

---

### usize

A random integer in [0, USize.max_value()]


```pony
fun ref usize()
: USize val
```

#### Returns

* [USize](builtin-USize) val

---

### i8

A random integer in [-2^7, 2^7)


```pony
fun ref i8()
: I8 val
```

#### Returns

* [I8](builtin-I8) val

---

### i16

A random integer in [-2^15, 2^15)


```pony
fun ref i16()
: I16 val
```

#### Returns

* [I16](builtin-I16) val

---

### i32

A random integer in [-2^31, 2^31)


```pony
fun ref i32()
: I32 val
```

#### Returns

* [I32](builtin-I32) val

---

### i64

A random integer in [-2^63, 2^63)


```pony
fun ref i64()
: I64 val
```

#### Returns

* [I64](builtin-I64) val

---

### i128

A random integer in [-2^127, 2^127)


```pony
fun ref i128()
: I128 val
```

#### Returns

* [I128](builtin-I128) val

---

### ilong

A random integer in [ILong.min_value(), ILong.max_value()]


```pony
fun ref ilong()
: ILong val
```

#### Returns

* [ILong](builtin-ILong) val

---

### isize

A random integer in [ISize.min_value(), ISize.max_value()]


```pony
fun ref isize()
: ISize val
```

#### Returns

* [ISize](builtin-ISize) val

---

### int\[optional N: (([U8](builtin-U8) val | [U16](builtin-U16) val | [U32](builtin-U32) val | [U64](builtin-U64) val | [U128](builtin-U128) val | [ULong](builtin-ULong) val | [USize](builtin-USize) val) & [Real](builtin-Real)\[N\] val)\]

A random integer in [0, n)


```pony
fun ref int[optional N: ((U8 val | U16 val | U32 val | 
    U64 val | U128 val | ULong val | 
    USize val) & Real[N] val)](
  n: N)
: N
```
#### Parameters

*   n: N

#### Returns

* N

---

### real

A random number in [0, 1)


```pony
fun ref real()
: F64 val
```

#### Returns

* [F64](builtin-F64) val

---

### shuffle\[A: A\]

Shuffle the elements of the array into a random order, mutating the array.


```pony
fun ref shuffle[A: A](
  array: Array[A] ref)
: None val
```
#### Parameters

*   array: [Array](builtin-Array)\[A\] ref

#### Returns

* [None](builtin-None) val

---

