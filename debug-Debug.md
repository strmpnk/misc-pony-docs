# Debug

This is a debug only print utility.


```pony
primitive val Debug
```

## Constructors

### create

```pony
new val create()
: Debug val^
```

#### Returns

* [Debug](debug-Debug) val^

---

## Public Functions

### out

If platform is debug configured, print message to standard output


```pony
fun box out(
  msg: Stringable box = seq)
: None val
```
#### Parameters

*   msg: [Stringable](builtin-Stringable) box = seq

#### Returns

* [None](builtin-None) val

---

### err

If platform is debug configured, print message to standard error


```pony
fun box err(
  msg: Stringable box = seq)
: None val
```
#### Parameters

*   msg: [Stringable](builtin-Stringable) box = seq

#### Returns

* [None](builtin-None) val

---

### apply

`apply(msg: Stringable, sep: String, stream: DebugStream): None`: If platform is debug configured, print a stringable. The default output
stream is stdout.


`apply(msg: ReadSeq[Stringable], sep: String, stream: DebugStream): None`: If platform is debug configured, print a sequence of stringables. The
default separator is ", ", and the default output stream is stdout.


```pony
fun box apply(
  msg: (Stringable box | ReadSeq[Stringable box] box),
  sep: String val = seq,
  stream: (DebugOut val | DebugErr val) = seq)
: None val
```
#### Parameters

*   msg: ([Stringable](builtin-Stringable) box | [ReadSeq](builtin-ReadSeq)\[[Stringable](builtin-Stringable) box\] box)
*   sep: [String](builtin-String) val = seq
*   stream: ([DebugOut](debug-DebugOut) val | [DebugErr](debug-DebugErr) val) = seq

#### Returns

* [None](builtin-None) val

---

### eq

```pony
fun box eq(
  that: Debug val)
: Bool val
```
#### Parameters

*   that: [Debug](debug-Debug) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: Debug val)
: Bool val
```
#### Parameters

*   that: [Debug](debug-Debug) val

#### Returns

* [Bool](builtin-Bool) val

---

## Private Functions

### _print

```pony
fun box _print(
  msg: String val,
  stream: (DebugOut val | DebugErr val))
: None val
```
#### Parameters

*   msg: [String](builtin-String) val
*   stream: ([DebugOut](debug-DebugOut) val | [DebugErr](debug-DebugErr) val)

#### Returns

* [None](builtin-None) val

---

### _stream

```pony
fun box _stream(
  stream: (DebugOut val | DebugErr val))
: Pointer[U8 val] ref
```
#### Parameters

*   stream: ([DebugOut](debug-DebugOut) val | [DebugErr](debug-DebugErr) val)

#### Returns

* [Pointer](builtin-Pointer)\[[U8](builtin-U8) val\] ref

---

