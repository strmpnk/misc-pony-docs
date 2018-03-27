# Reader

Store network data and provide a parsing interface.

`Reader` provides a way to extract typed data from a sequence of
bytes. The `Reader` manages the underlying data structures to
provide a read cursor over a contiguous sequence of bytes. It is
useful for decoding data that is received over a network or stored
in a file. Chunk of bytes are added to the `Reader` using the
`append` method, and typed data is extracted using the getter
methods.

For example, suppose we have a UDP-based network data protocol where
messages consist of the following:

* `list_size` - the number of items in the following list of items
  as a big-endian 32-bit integer
* zero or more items of the following data:
  * a big-endian 64-bit floating point number
  * a string that starts with a big-endian 32-bit integer that
    specifies the length of the string, followed by a number of
    bytes that represent the string

A message would be something like this:

```
[message_length][list_size][float1][string1][float2][string2]...
```

The following program uses a `Reader` to decode a message of
this type and print them:

```pony
use "buffered"
use "collections"

class Notify is StdinNotify
  let _env: Env
  new create(env: Env) =>
    _env = env
  fun ref apply(data: Array[U8] iso) =>
    let rb = Reader
    rb.append(consume data)
    try
      while true do
        let len = rb.i32_be()?
        let items = rb.i32_be()?.usize()
        for range in Range(0, items) do
          let f = rb.f32_be()?
          let str_len = rb.i32_be()?.usize()
          let str = String.from_array(rb.block(str_len)?)
          _env.out.print("[(" + f.string() + "), (" + str + ")]")
        end
      end
    end

actor Main
  new create(env: Env) =>
    env.input(recover Notify(env) end, 1024)
```


```pony
class ref Reader
```

## Constructors

### create

```pony
new iso create()
: Reader iso^
```

#### Returns

* [Reader](buffered-Reader) iso^

---

## Public Functions

### size

Return the number of available bytes.


```pony
fun box size()
: USize val
```

#### Returns

* [USize](builtin-USize) val

---

### clear

Discard all pending data.


```pony
fun ref clear()
: None val
```

#### Returns

* [None](builtin-None) val

---

### append

Add a chunk of data.


```pony
fun ref append(
  data: (String val | Array[U8 val] val))
: None val
```
#### Parameters

*   data: ([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)

#### Returns

* [None](builtin-None) val

---

### skip

Skip n bytes.


```pony
fun ref skip(
  n: USize val)
: None val ?
```
#### Parameters

*   n: [USize](builtin-USize) val

#### Returns

* [None](builtin-None) val ?

---

### block

Return a block as a contiguous chunk of memory.
Will throw an error if you request a block larger than what is currently
stored in the `Reader`.


```pony
fun ref block(
  len: USize val)
: Array[U8 val] iso^ ?
```
#### Parameters

*   len: [USize](builtin-USize) val

#### Returns

* [Array](builtin-Array)\[[U8](builtin-U8) val\] iso^ ?

---

### read_until

Find the first occurrence of the separator and return the block of bytes
before its position. The separator is not included in the returned array,
but it is removed from the buffer. To read a line of text, prefer line()
that handles \n and \r\n.


```pony
fun ref read_until(
  separator: U8 val)
: Array[U8 val] iso^ ?
```
#### Parameters

*   separator: [U8](builtin-U8) val

#### Returns

* [Array](builtin-Array)\[[U8](builtin-U8) val\] iso^ ?

---

### line

Return a \n or \r\n terminated line as a string. The newline is not
included in the returned string, but it is removed from the network buffer.


```pony
fun ref line()
: String val ?
```

#### Returns

* [String](builtin-String) val ?

---

### u8

Get a U8. Raise an error if there isn't enough data.


```pony
fun ref u8()
: U8 val ?
```

#### Returns

* [U8](builtin-U8) val ?

---

### i8

Get an I8.


```pony
fun ref i8()
: I8 val ?
```

#### Returns

* [I8](builtin-I8) val ?

---

### u16_be

Get a big-endian U16.


```pony
fun ref u16_be()
: U16 val ?
```

#### Returns

* [U16](builtin-U16) val ?

---

### u16_le

Get a little-endian U16.


```pony
fun ref u16_le()
: U16 val ?
```

#### Returns

* [U16](builtin-U16) val ?

---

### i16_be

Get a big-endian I16.


```pony
fun ref i16_be()
: I16 val ?
```

#### Returns

* [I16](builtin-I16) val ?

---

### i16_le

Get a little-endian I16.


```pony
fun ref i16_le()
: I16 val ?
```

#### Returns

* [I16](builtin-I16) val ?

---

### u32_be

Get a big-endian U32.


```pony
fun ref u32_be()
: U32 val ?
```

#### Returns

* [U32](builtin-U32) val ?

---

### u32_le

Get a little-endian U32.


```pony
fun ref u32_le()
: U32 val ?
```

#### Returns

* [U32](builtin-U32) val ?

---

### i32_be

Get a big-endian I32.


```pony
fun ref i32_be()
: I32 val ?
```

#### Returns

* [I32](builtin-I32) val ?

---

### i32_le

Get a little-endian I32.


```pony
fun ref i32_le()
: I32 val ?
```

#### Returns

* [I32](builtin-I32) val ?

---

### u64_be

Get a big-endian U64.


```pony
fun ref u64_be()
: U64 val ?
```

#### Returns

* [U64](builtin-U64) val ?

---

### u64_le

Get a little-endian U64.


```pony
fun ref u64_le()
: U64 val ?
```

#### Returns

* [U64](builtin-U64) val ?

---

### i64_be

Get a big-endian I64.


```pony
fun ref i64_be()
: I64 val ?
```

#### Returns

* [I64](builtin-I64) val ?

---

### i64_le

Get a little-endian I64.


```pony
fun ref i64_le()
: I64 val ?
```

#### Returns

* [I64](builtin-I64) val ?

---

### u128_be

Get a big-endian U128.


```pony
fun ref u128_be()
: U128 val ?
```

#### Returns

* [U128](builtin-U128) val ?

---

### u128_le

Get a little-endian U128.


```pony
fun ref u128_le()
: U128 val ?
```

#### Returns

* [U128](builtin-U128) val ?

---

### i128_be

Get a big-endian I129.


```pony
fun ref i128_be()
: I128 val ?
```

#### Returns

* [I128](builtin-I128) val ?

---

### i128_le

Get a little-endian I128.


```pony
fun ref i128_le()
: I128 val ?
```

#### Returns

* [I128](builtin-I128) val ?

---

### f32_be

Get a big-endian F32.


```pony
fun ref f32_be()
: F32 val ?
```

#### Returns

* [F32](builtin-F32) val ?

---

### f32_le

Get a little-endian F32.


```pony
fun ref f32_le()
: F32 val ?
```

#### Returns

* [F32](builtin-F32) val ?

---

### f64_be

Get a big-endian F64.


```pony
fun ref f64_be()
: F64 val ?
```

#### Returns

* [F64](builtin-F64) val ?

---

### f64_le

Get a little-endian F64.


```pony
fun ref f64_le()
: F64 val ?
```

#### Returns

* [F64](builtin-F64) val ?

---

### peek_u8

Peek at a U8 at the given offset. Raise an error if there isn't enough
data.


```pony
fun box peek_u8(
  offset: USize val = seq)
: U8 val ?
```
#### Parameters

*   offset: [USize](builtin-USize) val = seq

#### Returns

* [U8](builtin-U8) val ?

---

### peek_i8

Peek at an I8.


```pony
fun box peek_i8(
  offset: USize val = seq)
: I8 val ?
```
#### Parameters

*   offset: [USize](builtin-USize) val = seq

#### Returns

* [I8](builtin-I8) val ?

---

### peek_u16_be

Peek at a big-endian U16.


```pony
fun box peek_u16_be(
  offset: USize val = seq)
: U16 val ?
```
#### Parameters

*   offset: [USize](builtin-USize) val = seq

#### Returns

* [U16](builtin-U16) val ?

---

### peek_u16_le

Peek at a little-endian U16.


```pony
fun box peek_u16_le(
  offset: USize val = seq)
: U16 val ?
```
#### Parameters

*   offset: [USize](builtin-USize) val = seq

#### Returns

* [U16](builtin-U16) val ?

---

### peek_i16_be

Peek at a big-endian I16.


```pony
fun box peek_i16_be(
  offset: USize val = seq)
: I16 val ?
```
#### Parameters

*   offset: [USize](builtin-USize) val = seq

#### Returns

* [I16](builtin-I16) val ?

---

### peek_i16_le

Peek at a little-endian I16.


```pony
fun box peek_i16_le(
  offset: USize val = seq)
: I16 val ?
```
#### Parameters

*   offset: [USize](builtin-USize) val = seq

#### Returns

* [I16](builtin-I16) val ?

---

### peek_u32_be

Peek at a big-endian U32.


```pony
fun box peek_u32_be(
  offset: USize val = seq)
: U32 val ?
```
#### Parameters

*   offset: [USize](builtin-USize) val = seq

#### Returns

* [U32](builtin-U32) val ?

---

### peek_u32_le

Peek at a little-endian U32.


```pony
fun box peek_u32_le(
  offset: USize val = seq)
: U32 val ?
```
#### Parameters

*   offset: [USize](builtin-USize) val = seq

#### Returns

* [U32](builtin-U32) val ?

---

### peek_i32_be

Peek at a big-endian I32.


```pony
fun box peek_i32_be(
  offset: USize val = seq)
: I32 val ?
```
#### Parameters

*   offset: [USize](builtin-USize) val = seq

#### Returns

* [I32](builtin-I32) val ?

---

### peek_i32_le

Peek at a little-endian I32.


```pony
fun box peek_i32_le(
  offset: USize val = seq)
: I32 val ?
```
#### Parameters

*   offset: [USize](builtin-USize) val = seq

#### Returns

* [I32](builtin-I32) val ?

---

### peek_u64_be

Peek at a big-endian U64.


```pony
fun box peek_u64_be(
  offset: USize val = seq)
: U64 val ?
```
#### Parameters

*   offset: [USize](builtin-USize) val = seq

#### Returns

* [U64](builtin-U64) val ?

---

### peek_u64_le

Peek at a little-endian U64.


```pony
fun box peek_u64_le(
  offset: USize val = seq)
: U64 val ?
```
#### Parameters

*   offset: [USize](builtin-USize) val = seq

#### Returns

* [U64](builtin-U64) val ?

---

### peek_i64_be

Peek at a big-endian I64.


```pony
fun box peek_i64_be(
  offset: USize val = seq)
: I64 val ?
```
#### Parameters

*   offset: [USize](builtin-USize) val = seq

#### Returns

* [I64](builtin-I64) val ?

---

### peek_i64_le

Peek at a little-endian I64.


```pony
fun box peek_i64_le(
  offset: USize val = seq)
: I64 val ?
```
#### Parameters

*   offset: [USize](builtin-USize) val = seq

#### Returns

* [I64](builtin-I64) val ?

---

### peek_u128_be

Peek at a big-endian U128.


```pony
fun box peek_u128_be(
  offset: USize val = seq)
: U128 val ?
```
#### Parameters

*   offset: [USize](builtin-USize) val = seq

#### Returns

* [U128](builtin-U128) val ?

---

### peek_u128_le

Peek at a little-endian U128.


```pony
fun box peek_u128_le(
  offset: USize val = seq)
: U128 val ?
```
#### Parameters

*   offset: [USize](builtin-USize) val = seq

#### Returns

* [U128](builtin-U128) val ?

---

### peek_i128_be

Peek at a big-endian I129.


```pony
fun box peek_i128_be(
  offset: USize val = seq)
: I128 val ?
```
#### Parameters

*   offset: [USize](builtin-USize) val = seq

#### Returns

* [I128](builtin-I128) val ?

---

### peek_i128_le

Peek at a little-endian I128.


```pony
fun box peek_i128_le(
  offset: USize val = seq)
: I128 val ?
```
#### Parameters

*   offset: [USize](builtin-USize) val = seq

#### Returns

* [I128](builtin-I128) val ?

---

### peek_f32_be

Peek at a big-endian F32.


```pony
fun box peek_f32_be(
  offset: USize val = seq)
: F32 val ?
```
#### Parameters

*   offset: [USize](builtin-USize) val = seq

#### Returns

* [F32](builtin-F32) val ?

---

### peek_f32_le

Peek at a little-endian F32.


```pony
fun box peek_f32_le(
  offset: USize val = seq)
: F32 val ?
```
#### Parameters

*   offset: [USize](builtin-USize) val = seq

#### Returns

* [F32](builtin-F32) val ?

---

### peek_f64_be

Peek at a big-endian F64.


```pony
fun box peek_f64_be(
  offset: USize val = seq)
: F64 val ?
```
#### Parameters

*   offset: [USize](builtin-USize) val = seq

#### Returns

* [F64](builtin-F64) val ?

---

### peek_f64_le

Peek at a little-endian F64.


```pony
fun box peek_f64_le(
  offset: USize val = seq)
: F64 val ?
```
#### Parameters

*   offset: [USize](builtin-USize) val = seq

#### Returns

* [F64](builtin-F64) val ?

---

## Private Functions

### _byte

Get a single byte.


```pony
fun ref _byte()
: U8 val ?
```

#### Returns

* [U8](builtin-U8) val ?

---

### _peek_byte

Get the byte at the given offset without moving the cursor forward.
Raise an error if the given offset is not yet available.


```pony
fun box _peek_byte(
  offset: USize val = seq)
: U8 val ?
```
#### Parameters

*   offset: [USize](builtin-USize) val = seq

#### Returns

* [U8](builtin-U8) val ?

---

### _distance_of

Get the distance to the first occurrence of the given byte


```pony
fun ref _distance_of(
  byte: U8 val)
: USize val ?
```
#### Parameters

*   byte: [U8](builtin-U8) val

#### Returns

* [USize](builtin-USize) val ?

---

### _search_length

Get the length of a pending line. Raise an error if there is no pending
line.


```pony
fun ref _search_length()
: USize val ?
```

#### Returns

* [USize](builtin-USize) val ?

---

