# CapRights0

Version 0 of the capsicum cap_rights_t structure.


```pony
class ref CapRights0
```

## Constructors

### create

```pony
new ref create()
: CapRights0 ref^
```

#### Returns

* [CapRights0](capsicum-CapRights0) ref^

---

### from

```pony
new ref from(
  caps: Flags[(FileCreate val | FileChmod val | FileChown val | FileLink val | FileLookup val | FileMkdir val | FileRead val | FileRemove val | FileRename val | FileSeek val | FileStat val | FileSync val | FileTime val | FileTruncate val | FileWrite val | FileExec val), U32 val] box)
: CapRights0 ref^
```
#### Parameters

*   caps: [Flags](collections-Flags)\[([FileCreate](files-FileCreate) val | [FileChmod](files-FileChmod) val | [FileChown](files-FileChown) val | [FileLink](files-FileLink) val | [FileLookup](files-FileLookup) val | [FileMkdir](files-FileMkdir) val | [FileRead](files-FileRead) val | [FileRemove](files-FileRemove) val | [FileRename](files-FileRename) val | [FileSeek](files-FileSeek) val | [FileStat](files-FileStat) val | [FileSync](files-FileSync) val | [FileTime](files-FileTime) val | [FileTruncate](files-FileTruncate) val | [FileWrite](files-FileWrite) val | [FileExec](files-FileExec) val), [U32](builtin-U32) val\] box

#### Returns

* [CapRights0](capsicum-CapRights0) ref^

---

### descriptor

```pony
new ref descriptor(
  fd: I32 val)
: CapRights0 ref^
```
#### Parameters

*   fd: [I32](builtin-I32) val

#### Returns

* [CapRights0](capsicum-CapRights0) ref^

---

## Public Functions

### set

```pony
fun ref set(
  cap: U64 val)
: None val
```
#### Parameters

*   cap: [U64](builtin-U64) val

#### Returns

* [None](builtin-None) val

---

### unset

```pony
fun ref unset(
  cap: U64 val)
: None val
```
#### Parameters

*   cap: [U64](builtin-U64) val

#### Returns

* [None](builtin-None) val

---

### limit

Limits the fd to the encoded rights.


```pony
fun box limit(
  fd: I32 val)
: Bool val
```
#### Parameters

*   fd: [I32](builtin-I32) val

#### Returns

* [Bool](builtin-Bool) val

---

### merge

Merge the rights in that into this.


```pony
fun ref merge(
  that: CapRights0 ref)
: None val
```
#### Parameters

*   that: [CapRights0](capsicum-CapRights0) ref

#### Returns

* [None](builtin-None) val

---

### remove

Remove the rights in that from this.


```pony
fun ref remove(
  that: CapRights0 ref)
: None val
```
#### Parameters

*   that: [CapRights0](capsicum-CapRights0) ref

#### Returns

* [None](builtin-None) val

---

### clear

Clear all rights.


```pony
fun ref clear()
: None val
```

#### Returns

* [None](builtin-None) val

---

### contains

Check that this is a superset of the rights in that.


```pony
fun box contains(
  that: CapRights0 ref)
: Bool val
```
#### Parameters

*   that: [CapRights0](capsicum-CapRights0) ref

#### Returns

* [Bool](builtin-Bool) val

---

## Private Functions

### _version

```pony
fun box _version()
: I32 val
```

#### Returns

* [I32](builtin-I32) val

---

