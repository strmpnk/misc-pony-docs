# _FileDes

Convenience operations on file descriptors.


```pony
primitive val _FileDes
```

## Constructors

### create

```pony
new val create()
: _FileDes val^
```

#### Returns

* [_FileDes](files-_FileDes) val^

---

## Public Functions

### chmod

Set the FileMode for this fd.


```pony
fun box chmod(
  fd: I32 val,
  path: FilePath val,
  mode: FileMode box)
: Bool val
```
#### Parameters

*   fd: [I32](builtin-I32) val
*   path: [FilePath](files-FilePath) val
*   mode: [FileMode](files-FileMode) box

#### Returns

* [Bool](builtin-Bool) val

---

### chown

Set the owner and group for this file. Does nothing on Windows.


```pony
fun box chown(
  fd: I32 val,
  path: FilePath val,
  uid: U32 val,
  gid: U32 val)
: Bool val
```
#### Parameters

*   fd: [I32](builtin-I32) val
*   path: [FilePath](files-FilePath) val
*   uid: [U32](builtin-U32) val
*   gid: [U32](builtin-U32) val

#### Returns

* [Bool](builtin-Bool) val

---

### touch

Set the last access and modification times of the file to now.


```pony
fun box touch(
  fd: I32 val,
  path: FilePath val)
: Bool val
```
#### Parameters

*   fd: [I32](builtin-I32) val
*   path: [FilePath](files-FilePath) val

#### Returns

* [Bool](builtin-Bool) val

---

### set_time

Set the last access and modification times of the file to the given values.


```pony
fun box set_time(
  fd: I32 val,
  path: FilePath val,
  atime: (I64 val , I64 val),
  mtime: (I64 val , I64 val))
: Bool val
```
#### Parameters

*   fd: [I32](builtin-I32) val
*   path: [FilePath](files-FilePath) val
*   atime: ([I64](builtin-I64) val , [I64](builtin-I64) val)
*   mtime: ([I64](builtin-I64) val , [I64](builtin-I64) val)

#### Returns

* [Bool](builtin-Bool) val

---

### set_rights

Set the Capsicum rights on the file descriptor.


```pony
fun box set_rights(
  fd: I32 val,
  path: FilePath val,
  writeable: Bool val = seq)
: None val ?
```
#### Parameters

*   fd: [I32](builtin-I32) val
*   path: [FilePath](files-FilePath) val
*   writeable: [Bool](builtin-Bool) val = seq

#### Returns

* [None](builtin-None) val ?

---

### eq

```pony
fun box eq(
  that: _FileDes val)
: Bool val
```
#### Parameters

*   that: [_FileDes](files-_FileDes) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: _FileDes val)
: Bool val
```
#### Parameters

*   that: [_FileDes](files-_FileDes) val

#### Returns

* [Bool](builtin-Bool) val

---

