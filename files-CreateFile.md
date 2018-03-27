# CreateFile

Open a File for read/write, creating if it doesn't exist, preserving the
contents if it does exist.


```pony
primitive val CreateFile
```

## Constructors

### create

```pony
new val create()
: CreateFile val^
```

#### Returns

* [CreateFile](files-CreateFile) val^

---

## Public Functions

### apply

```pony
fun box apply(
  from: FilePath val)
: (File ref | FileOK val | FileError val | 
    FileEOF val | FileBadFileNumber val | FileExists val | 
    FilePermissionDenied val)
```
#### Parameters

*   from: [FilePath](files-FilePath) val

#### Returns

* ([File](files-File) ref | [FileOK](files-FileOK) val | [FileError](files-FileError) val | 
    [FileEOF](files-FileEOF) val | [FileBadFileNumber](files-FileBadFileNumber) val | [FileExists](files-FileExists) val | 
    [FilePermissionDenied](files-FilePermissionDenied) val)

---

### eq

```pony
fun box eq(
  that: CreateFile val)
: Bool val
```
#### Parameters

*   that: [CreateFile](files-CreateFile) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: CreateFile val)
: Bool val
```
#### Parameters

*   that: [CreateFile](files-CreateFile) val

#### Returns

* [Bool](builtin-Bool) val

---

