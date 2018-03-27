# Directory

Operations on a directory.

The directory-relative functions (open, etc) use the *at interface on FreeBSD
and Linux. This isn't available on OS X prior to 10.10, so it is not used. On
FreeBSD, this allows the directory-relative functions to take advantage of
Capsicum.


```pony
class ref Directory
```

## Constructors

### create

```pony
new ref create(
  from: FilePath val)
: Directory ref^ ?
```
#### Parameters

*   from: [FilePath](files-FilePath) val

#### Returns

* [Directory](files-Directory) ref^ ?

---

### _relative

```pony
new iso _relative(
  path': FilePath val,
  fd': I32 val)
: Directory iso^
```
#### Parameters

*   path': [FilePath](files-FilePath) val
*   fd': [I32](builtin-I32) val

#### Returns

* [Directory](files-Directory) iso^

---

## Public fields

* let path: [FilePath](files-FilePath) val

---

## Public Functions

### entries

The entries will include everything in the directory, but it is not
recursive. The path for the entry will be relative to the directory, so it
will contain no directory separators. The entries will not include "." or
"..".


```pony
fun box entries()
: Array[String val] iso^ ?
```

#### Returns

* [Array](builtin-Array)\[[String](builtin-String) val\] iso^ ?

---

### open

Open a directory relative to this one. Raises an error if the path is not
within this directory hierarchy.


```pony
fun box open(
  target: String val)
: Directory iso^ ?
```
#### Parameters

*   target: [String](builtin-String) val

#### Returns

* [Directory](files-Directory) iso^ ?

---

### mkdir

Creates a directory relative to this one. Returns false if the path is
not within this directory hierarchy or if FileMkdir permission is missing.


```pony
fun box mkdir(
  target: String val)
: Bool val
```
#### Parameters

*   target: [String](builtin-String) val

#### Returns

* [Bool](builtin-Bool) val

---

### create_file

Open for read/write, creating if it doesn't exist, preserving the contents
if it does exist.


```pony
fun box create_file(
  target: String val)
: File iso^ ?
```
#### Parameters

*   target: [String](builtin-String) val

#### Returns

* [File](files-File) iso^ ?

---

### open_file

Open for read only, failing if it doesn't exist.


```pony
fun box open_file(
  target: String val)
: File iso^ ?
```
#### Parameters

*   target: [String](builtin-String) val

#### Returns

* [File](files-File) iso^ ?

---

### info

Return a FileInfo for this directory. Raise an error if the fd is invalid
or if we don't have FileStat permission.


```pony
fun box info()
: FileInfo val ?
```

#### Returns

* [FileInfo](files-FileInfo) val ?

---

### chmod

Set the FileMode for this directory.


```pony
fun box chmod(
  mode: FileMode box)
: Bool val
```
#### Parameters

*   mode: [FileMode](files-FileMode) box

#### Returns

* [Bool](builtin-Bool) val

---

### chown

Set the owner and group for this directory. Does nothing on Windows.


```pony
fun box chown(
  uid: U32 val,
  gid: U32 val)
: Bool val
```
#### Parameters

*   uid: [U32](builtin-U32) val
*   gid: [U32](builtin-U32) val

#### Returns

* [Bool](builtin-Bool) val

---

### touch

Set the last access and modification times of the directory to now.


```pony
fun box touch()
: Bool val
```

#### Returns

* [Bool](builtin-Bool) val

---

### set_time

Set the last access and modification times of the directory to the given
values.


```pony
fun box set_time(
  atime: (I64 val , I64 val),
  mtime: (I64 val , I64 val))
: Bool val
```
#### Parameters

*   atime: ([I64](builtin-I64) val , [I64](builtin-I64) val)
*   mtime: ([I64](builtin-I64) val , [I64](builtin-I64) val)

#### Returns

* [Bool](builtin-Bool) val

---

### infoat

Return a FileInfo for some path relative to this directory.


```pony
fun box infoat(
  target: String val)
: FileInfo val ?
```
#### Parameters

*   target: [String](builtin-String) val

#### Returns

* [FileInfo](files-FileInfo) val ?

---

### chmodat

Set the FileMode for some path relative to this directory.


```pony
fun box chmodat(
  target: String val,
  mode: FileMode box)
: Bool val
```
#### Parameters

*   target: [String](builtin-String) val
*   mode: [FileMode](files-FileMode) box

#### Returns

* [Bool](builtin-Bool) val

---

### chownat

Set the FileMode for some path relative to this directory.


```pony
fun box chownat(
  target: String val,
  uid: U32 val,
  gid: U32 val)
: Bool val
```
#### Parameters

*   target: [String](builtin-String) val
*   uid: [U32](builtin-U32) val
*   gid: [U32](builtin-U32) val

#### Returns

* [Bool](builtin-Bool) val

---

### touchat

Set the last access and modification times of the directory to now.


```pony
fun box touchat(
  target: String val)
: Bool val
```
#### Parameters

*   target: [String](builtin-String) val

#### Returns

* [Bool](builtin-Bool) val

---

### set_time_at

Set the last access and modification times of the directory to the given
values.


```pony
fun box set_time_at(
  target: String val,
  atime: (I64 val , I64 val),
  mtime: (I64 val , I64 val))
: Bool val
```
#### Parameters

*   target: [String](builtin-String) val
*   atime: ([I64](builtin-I64) val , [I64](builtin-I64) val)
*   mtime: ([I64](builtin-I64) val , [I64](builtin-I64) val)

#### Returns

* [Bool](builtin-Bool) val

---

### symlink

Link the source path to the link_name, where the link_name is relative to
this directory.


```pony
fun box symlink(
  source: FilePath val,
  link_name: String val)
: Bool val
```
#### Parameters

*   source: [FilePath](files-FilePath) val
*   link_name: [String](builtin-String) val

#### Returns

* [Bool](builtin-Bool) val

---

### remove

Remove the file or directory. The directory contents will be removed as
well, recursively. Symlinks will be removed but not traversed.


```pony
fun box remove(
  target: String val)
: Bool val
```
#### Parameters

*   target: [String](builtin-String) val

#### Returns

* [Bool](builtin-Bool) val

---

### rename

Rename source (which is relative to this directory) to target (which is
relative to the `to` directory).


```pony
fun box rename(
  source: String val,
  to: Directory box,
  target: String val)
: Bool val
```
#### Parameters

*   source: [String](builtin-String) val
*   to: [Directory](files-Directory) box
*   target: [String](builtin-String) val

#### Returns

* [Bool](builtin-Bool) val

---

### dispose

Close the directory.


```pony
fun ref dispose()
: None val
```

#### Returns

* [None](builtin-None) val

---

## Private Functions

### _final

Close the file descriptor.


```pony
fun box _final()
: None val
```

#### Returns

* [None](builtin-None) val

---

