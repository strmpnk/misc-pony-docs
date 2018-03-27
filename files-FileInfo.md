# FileInfo

This contains file system metadata for a path. The times are in the same
format as Time.now(), i.e. seconds and nanoseconds since the epoch.

The INODE is UNIX specific. It will be zero on Windows.

The UID and GID are UNIX-style user and group IDs. These will be zero on
Windows. The change_time will actually be the file creation time on Windows.

A symlink will report information about itself, other than the size which
will be the size of the target. A broken symlink will report as much as it
can and will set the broken flag.


```pony
class val FileInfo
```

## Constructors

### create

```pony
new val create(
  from: FilePath val)
: FileInfo val^ ?
```
#### Parameters

*   from: [FilePath](files-FilePath) val

#### Returns

* [FileInfo](files-FileInfo) val^ ?

---

### _descriptor

```pony
new val _descriptor(
  fd: I32 val,
  path: FilePath val)
: FileInfo val^ ?
```
#### Parameters

*   fd: [I32](builtin-I32) val
*   path: [FilePath](files-FilePath) val

#### Returns

* [FileInfo](files-FileInfo) val^ ?

---

### _relative

```pony
new val _relative(
  fd: I32 val,
  path: FilePath val,
  from: String val)
: FileInfo val^ ?
```
#### Parameters

*   fd: [I32](builtin-I32) val
*   path: [FilePath](files-FilePath) val
*   from: [String](builtin-String) val

#### Returns

* [FileInfo](files-FileInfo) val^ ?

---

## Public fields

* let filepath: [FilePath](files-FilePath) val

---

* let mode: [FileMode](files-FileMode) val

---

* let hard_links: [U32](builtin-U32) val

---

* let device: [U64](builtin-U64) val

---

* let inode: [U64](builtin-U64) val

---

* let uid: [U32](builtin-U32) val

---

* let gid: [U32](builtin-U32) val

---

* let size: [USize](builtin-USize) val

---

* let access_time: ([I64](builtin-I64) val , [I64](builtin-I64) val)

---

* let modified_time: ([I64](builtin-I64) val , [I64](builtin-I64) val)

---

* let change_time: ([I64](builtin-I64) val , [I64](builtin-I64) val)

---

* let file: [Bool](builtin-Bool) val

---

* let directory: [Bool](builtin-Bool) val

---

* let pipe: [Bool](builtin-Bool) val

---

* let symlink: [Bool](builtin-Bool) val

---

* let broken: [Bool](builtin-Bool) val

---

