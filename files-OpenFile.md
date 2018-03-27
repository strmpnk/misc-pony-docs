# OpenFile

Open a File for read only.


```pony
primitive val OpenFile
```

## Constructors

### create

```pony
new val create()
: OpenFile val^
```

#### Returns

* [OpenFile](files-OpenFile) val^

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
  that: OpenFile val)
: Bool val
```
#### Parameters

*   that: [OpenFile](files-OpenFile) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: OpenFile val)
: Bool val
```
#### Parameters

*   that: [OpenFile](files-OpenFile) val

#### Returns

* [Bool](builtin-Bool) val

---

