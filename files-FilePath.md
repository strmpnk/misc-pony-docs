# FilePath

A FilePath represents a capability to access a path. The path will be
represented as an absolute path and a set of capabilities for operations on
that path.


```pony
class val FilePath
```

## Constructors

### create

```pony
new val create(
  base: (FilePath val | AmbientAuth val),
  path': String val,
  caps': Flags[(FileCreate val | FileChmod val | FileChown val | FileLink val | FileLookup val | FileMkdir val | FileRead val | FileRemove val | FileRename val | FileSeek val | FileStat val | FileSync val | FileTime val | FileTruncate val | FileWrite val | FileExec val), U32 val] val = seq)
: FilePath val^ ?
```
#### Parameters

*   base: ([FilePath](files-FilePath) val | [AmbientAuth](builtin-AmbientAuth) val)
*   path': [String](builtin-String) val
*   caps': [Flags](collections-Flags)\[([FileCreate](files-FileCreate) val | [FileChmod](files-FileChmod) val | [FileChown](files-FileChown) val | [FileLink](files-FileLink) val | [FileLookup](files-FileLookup) val | [FileMkdir](files-FileMkdir) val | [FileRead](files-FileRead) val | [FileRemove](files-FileRemove) val | [FileRename](files-FileRename) val | [FileSeek](files-FileSeek) val | [FileStat](files-FileStat) val | [FileSync](files-FileSync) val | [FileTime](files-FileTime) val | [FileTruncate](files-FileTruncate) val | [FileWrite](files-FileWrite) val | [FileExec](files-FileExec) val), [U32](builtin-U32) val\] val = seq

#### Returns

* [FilePath](files-FilePath) val^ ?

---

### mkdtemp

```pony
new val mkdtemp(
  base: (FilePath val | AmbientAuth val),
  prefix: String val = seq,
  caps': Flags[(FileCreate val | FileChmod val | FileChown val | FileLink val | FileLookup val | FileMkdir val | FileRead val | FileRemove val | FileRename val | FileSeek val | FileStat val | FileSync val | FileTime val | FileTruncate val | FileWrite val | FileExec val), U32 val] val = seq)
: FilePath val^ ?
```
#### Parameters

*   base: ([FilePath](files-FilePath) val | [AmbientAuth](builtin-AmbientAuth) val)
*   prefix: [String](builtin-String) val = seq
*   caps': [Flags](collections-Flags)\[([FileCreate](files-FileCreate) val | [FileChmod](files-FileChmod) val | [FileChown](files-FileChown) val | [FileLink](files-FileLink) val | [FileLookup](files-FileLookup) val | [FileMkdir](files-FileMkdir) val | [FileRead](files-FileRead) val | [FileRemove](files-FileRemove) val | [FileRename](files-FileRename) val | [FileSeek](files-FileSeek) val | [FileStat](files-FileStat) val | [FileSync](files-FileSync) val | [FileTime](files-FileTime) val | [FileTruncate](files-FileTruncate) val | [FileWrite](files-FileWrite) val | [FileExec](files-FileExec) val), [U32](builtin-U32) val\] val = seq

#### Returns

* [FilePath](files-FilePath) val^ ?

---

### _create

```pony
new val _create(
  path': String val,
  caps': Flags[(FileCreate val | FileChmod val | FileChown val | FileLink val | FileLookup val | FileMkdir val | FileRead val | FileRemove val | FileRename val | FileSeek val | FileStat val | FileSync val | FileTime val | FileTruncate val | FileWrite val | FileExec val), U32 val] val)
: FilePath val^
```
#### Parameters

*   path': [String](builtin-String) val
*   caps': [Flags](collections-Flags)\[([FileCreate](files-FileCreate) val | [FileChmod](files-FileChmod) val | [FileChown](files-FileChown) val | [FileLink](files-FileLink) val | [FileLookup](files-FileLookup) val | [FileMkdir](files-FileMkdir) val | [FileRead](files-FileRead) val | [FileRemove](files-FileRemove) val | [FileRename](files-FileRename) val | [FileSeek](files-FileSeek) val | [FileStat](files-FileStat) val | [FileSync](files-FileSync) val | [FileTime](files-FileTime) val | [FileTruncate](files-FileTruncate) val | [FileWrite](files-FileWrite) val | [FileExec](files-FileExec) val), [U32](builtin-U32) val\] val

#### Returns

* [FilePath](files-FilePath) val^

---

## Public fields

* let path: [String](builtin-String) val

---

* let caps: [Flags](collections-Flags)\[([FileCreate](files-FileCreate) val | [FileChmod](files-FileChmod) val | [FileChown](files-FileChown) val | [FileLink](files-FileLink) val | [FileLookup](files-FileLookup) val | [FileMkdir](files-FileMkdir) val | [FileRead](files-FileRead) val | [FileRemove](files-FileRemove) val | [FileRename](files-FileRename) val | [FileSeek](files-FileSeek) val | [FileStat](files-FileStat) val | [FileSync](files-FileSync) val | [FileTime](files-FileTime) val | [FileTruncate](files-FileTruncate) val | [FileWrite](files-FileWrite) val | [FileExec](files-FileExec) val), [U32](builtin-U32) val\] ref

---

## Public Functions

### join

Return a new path relative to this one.


```pony
fun val join(
  path': String val,
  caps': Flags[(FileCreate val | FileChmod val | FileChown val | FileLink val | FileLookup val | FileMkdir val | FileRead val | FileRemove val | FileRename val | FileSeek val | FileStat val | FileSync val | FileTime val | FileTruncate val | FileWrite val | FileExec val), U32 val] val = seq)
: FilePath val ?
```
#### Parameters

*   path': [String](builtin-String) val
*   caps': [Flags](collections-Flags)\[([FileCreate](files-FileCreate) val | [FileChmod](files-FileChmod) val | [FileChown](files-FileChown) val | [FileLink](files-FileLink) val | [FileLookup](files-FileLookup) val | [FileMkdir](files-FileMkdir) val | [FileRead](files-FileRead) val | [FileRemove](files-FileRemove) val | [FileRename](files-FileRename) val | [FileSeek](files-FileSeek) val | [FileStat](files-FileStat) val | [FileSync](files-FileSync) val | [FileTime](files-FileTime) val | [FileTruncate](files-FileTruncate) val | [FileWrite](files-FileWrite) val | [FileExec](files-FileExec) val), [U32](builtin-U32) val\] val = seq

#### Returns

* [FilePath](files-FilePath) val ?

---

### walk

Walks a directory structure starting at this.

`handler(dir_path, dir_entries)` will be called for each directory
starting with this one. The handler can control which subdirectories are
expanded by removing them from the `dir_entries` list.


```pony
fun val walk(
  handler: WalkHandler ref,
  follow_links: Bool val = seq)
: None val
```
#### Parameters

*   handler: [WalkHandler](files-WalkHandler) ref
*   follow_links: [Bool](builtin-Bool) val = seq

#### Returns

* [None](builtin-None) val

---

### canonical

Return the equivalent canonical absolute path. Raise an error if there
isn't one.


```pony
fun val canonical()
: FilePath val ?
```

#### Returns

* [FilePath](files-FilePath) val ?

---

### exists

Returns true if the path exists. Returns false for a broken symlink.


```pony
fun val exists()
: Bool val
```

#### Returns

* [Bool](builtin-Bool) val

---

### mkdir

Creates the directory. Will recursively create each element. Returns true
if the directory exists when we're done, false if it does not. If we do not
have the FileStat permission, this will return false even if the directory
does exist.


```pony
fun val mkdir(
  must_create: Bool val = seq)
: Bool val
```
#### Parameters

*   must_create: [Bool](builtin-Bool) val = seq

#### Returns

* [Bool](builtin-Bool) val

---

### remove

Remove the file or directory. The directory contents will be removed as
well, recursively. Symlinks will be removed but not traversed.


```pony
fun val remove()
: Bool val
```

#### Returns

* [Bool](builtin-Bool) val

---

### rename

Rename a file or directory.


```pony
fun box rename(
  new_path: FilePath val)
: Bool val
```
#### Parameters

*   new_path: [FilePath](files-FilePath) val

#### Returns

* [Bool](builtin-Bool) val

---

### symlink

Create a symlink to a file or directory.


```pony
fun box symlink(
  link_name: FilePath val)
: Bool val
```
#### Parameters

*   link_name: [FilePath](files-FilePath) val

#### Returns

* [Bool](builtin-Bool) val

---

### chmod

Set the FileMode for a path.


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

Set the owner and group for a path. Does nothing on Windows.


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

Set the last access and modification times of a path to now.


```pony
fun box touch()
: Bool val
```

#### Returns

* [Bool](builtin-Bool) val

---

### set_time

Set the last access and modification times of a path to the given values.


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

