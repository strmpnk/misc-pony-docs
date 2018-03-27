# Writer

A buffer for building messages.

`Writer` provides an way to create byte sequences using common
data encodings. The `Writer` manages the underlying arrays and
sizes. It is useful for encoding data to send over a network or
store in a file. Once a message has been built you can call `done()`
to get the message's `ByteSeq`s, and you can then reuse the
`Writer` for creating a new message.

For example, suppose we have a TCP-based network data protocol where
messages consist of the following:

* `message_length` - the number of bytes in the message as a
  big-endian 32-bit integer
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

The following program uses a write buffer to encode an array of
tuples as a message of this type:

```pony
use "buffered"

actor Main
  new create(env: Env) =>
    let wb = Writer
    let messages = [[(F32(3597.82), "Anderson"); (F32(-7979.3), "Graham")]
                    [(F32(3.14159), "Hopper"); (F32(-83.83), "Jones")]]
    for items in messages.values() do
      wb.i32_be((items.size() / 2).i32())
      for (f, s) in items.values() do
        wb.f32_be(f)
        wb.i32_be(s.size().i32())
        wb.write(s.array())
      end
      let wb_msg = Writer
      wb_msg.i32_be(wb.size().i32())
      wb_msg.writev(wb.done())
      env.out.writev(wb_msg.done())
    end
```


```pony
class ref Writer
```

## Constructors

### create

```pony
new iso create()
: Writer iso^
```

#### Returns

* [Writer](buffered-Writer) iso^

---

## Public Functions

### reserve_chunks

Reserve space for size' chunks.

This needs to be recalled after every call to `done`
as `done` resets the chunks.


```pony
fun ref reserve_chunks(
  size': USize val)
: None val
```
#### Parameters

*   size': [USize](builtin-USize) val

#### Returns

* [None](builtin-None) val

---

### reserve_current

Reserve space for size bytes in `_current`.


```pony
fun ref reserve_current(
  size': USize val)
: None val
```
#### Parameters

*   size': [USize](builtin-USize) val

#### Returns

* [None](builtin-None) val

---

### size

```pony
fun box size()
: USize val
```

#### Returns

* [USize](builtin-USize) val

---

### u8

Write a byte to the buffer.


```pony
fun ref u8(
  data: U8 val)
: None val
```
#### Parameters

*   data: [U8](builtin-U8) val

#### Returns

* [None](builtin-None) val

---

### u16_le

Write a U16 to the buffer in little-endian byte order.


```pony
fun ref u16_le(
  data: U16 val)
: None val
```
#### Parameters

*   data: [U16](builtin-U16) val

#### Returns

* [None](builtin-None) val

---

### u16_be

Write a U16 to the buffer in big-endian byte order.


```pony
fun ref u16_be(
  data: U16 val)
: None val
```
#### Parameters

*   data: [U16](builtin-U16) val

#### Returns

* [None](builtin-None) val

---

### i16_le

Write an I16 to the buffer in little-endian byte order.


```pony
fun ref i16_le(
  data: I16 val)
: None val
```
#### Parameters

*   data: [I16](builtin-I16) val

#### Returns

* [None](builtin-None) val

---

### i16_be

Write an I16 to the buffer in big-endian byte order.


```pony
fun ref i16_be(
  data: I16 val)
: None val
```
#### Parameters

*   data: [I16](builtin-I16) val

#### Returns

* [None](builtin-None) val

---

### u32_le

Write a U32 to the buffer in little-endian byte order.


```pony
fun ref u32_le(
  data: U32 val)
: None val
```
#### Parameters

*   data: [U32](builtin-U32) val

#### Returns

* [None](builtin-None) val

---

### u32_be

Write a U32 to the buffer in big-endian byte order.


```pony
fun ref u32_be(
  data: U32 val)
: None val
```
#### Parameters

*   data: [U32](builtin-U32) val

#### Returns

* [None](builtin-None) val

---

### i32_le

Write an I32 to the buffer in little-endian byte order.


```pony
fun ref i32_le(
  data: I32 val)
: None val
```
#### Parameters

*   data: [I32](builtin-I32) val

#### Returns

* [None](builtin-None) val

---

### i32_be

Write an I32 to the buffer in big-endian byte order.


```pony
fun ref i32_be(
  data: I32 val)
: None val
```
#### Parameters

*   data: [I32](builtin-I32) val

#### Returns

* [None](builtin-None) val

---

### f32_le

Write an F32 to the buffer in little-endian byte order.


```pony
fun ref f32_le(
  data: F32 val)
: None val
```
#### Parameters

*   data: [F32](builtin-F32) val

#### Returns

* [None](builtin-None) val

---

### f32_be

Write an F32 to the buffer in big-endian byte order.


```pony
fun ref f32_be(
  data: F32 val)
: None val
```
#### Parameters

*   data: [F32](builtin-F32) val

#### Returns

* [None](builtin-None) val

---

### u64_le

Write a U64 to the buffer in little-endian byte order.


```pony
fun ref u64_le(
  data: U64 val)
: None val
```
#### Parameters

*   data: [U64](builtin-U64) val

#### Returns

* [None](builtin-None) val

---

### u64_be

Write a U64 to the buffer in big-endian byte order.


```pony
fun ref u64_be(
  data: U64 val)
: None val
```
#### Parameters

*   data: [U64](builtin-U64) val

#### Returns

* [None](builtin-None) val

---

### i64_le

Write an I64 to the buffer in little-endian byte order.


```pony
fun ref i64_le(
  data: I64 val)
: None val
```
#### Parameters

*   data: [I64](builtin-I64) val

#### Returns

* [None](builtin-None) val

---

### i64_be

Write an I64 to the buffer in big-endian byte order.


```pony
fun ref i64_be(
  data: I64 val)
: None val
```
#### Parameters

*   data: [I64](builtin-I64) val

#### Returns

* [None](builtin-None) val

---

### f64_le

Write an F64 to the buffer in little-endian byte order.


```pony
fun ref f64_le(
  data: F64 val)
: None val
```
#### Parameters

*   data: [F64](builtin-F64) val

#### Returns

* [None](builtin-None) val

---

### f64_be

Write an F64 to the buffer in big-endian byte order.


```pony
fun ref f64_be(
  data: F64 val)
: None val
```
#### Parameters

*   data: [F64](builtin-F64) val

#### Returns

* [None](builtin-None) val

---

### u128_le

Write a U128 to the buffer in little-endian byte order.


```pony
fun ref u128_le(
  data: U128 val)
: None val
```
#### Parameters

*   data: [U128](builtin-U128) val

#### Returns

* [None](builtin-None) val

---

### u128_be

Write a U128 to the buffer in big-endian byte order.


```pony
fun ref u128_be(
  data: U128 val)
: None val
```
#### Parameters

*   data: [U128](builtin-U128) val

#### Returns

* [None](builtin-None) val

---

### i128_le

Write an I128 to the buffer in little-endian byte order.


```pony
fun ref i128_le(
  data: I128 val)
: None val
```
#### Parameters

*   data: [I128](builtin-I128) val

#### Returns

* [None](builtin-None) val

---

### i128_be

Write an I128 to the buffer in big-endian byte order.


```pony
fun ref i128_be(
  data: I128 val)
: None val
```
#### Parameters

*   data: [I128](builtin-I128) val

#### Returns

* [None](builtin-None) val

---

### write

Write a ByteSeq to the buffer.


```pony
fun ref write(
  data: (String val | Array[U8 val] val))
: None val
```
#### Parameters

*   data: ([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)

#### Returns

* [None](builtin-None) val

---

### writev

Write ByteSeqs to the buffer.


```pony
fun ref writev(
  data: ByteSeqIter val)
: None val
```
#### Parameters

*   data: [ByteSeqIter](builtin-ByteSeqIter) val

#### Returns

* [None](builtin-None) val

---

### done

Return an array of buffered ByteSeqs and reset the Writer's buffer.


```pony
fun ref done()
: Array[(String val | Array[U8 val] val)] iso^
```

#### Returns

* [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] iso^

---

## Private Functions

### _append_current

```pony
fun ref _append_current()
: None val
```

#### Returns

* [None](builtin-None) val

---

### _check

```pony
fun ref _check(
  size': USize val)
: None val
```
#### Parameters

*   size': [USize](builtin-USize) val

#### Returns

* [None](builtin-None) val

---

### _byte

```pony
fun ref _byte(
  data: U8 val)
: None val
```
#### Parameters

*   data: [U8](builtin-U8) val

#### Returns

* [None](builtin-None) val

---

