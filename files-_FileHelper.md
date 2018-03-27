# _FileHelper

```pony
primitive val _FileHelper
```

## Constructors

### create

```pony
new val create()
: _FileHelper val^
```

#### Returns

* [_FileHelper](files-_FileHelper) val^

---

## Public Functions

### make_files

```pony
fun box make_files(
  h: TestHelper val,
  files: Array[String val] ref)
: FilePath val ?
```
#### Parameters

*   h: [TestHelper](ponytest-TestHelper) val
*   files: [Array](builtin-Array)\[[String](builtin-String) val\] ref

#### Returns

* [FilePath](files-FilePath) val ?

---

### eq

```pony
fun box eq(
  that: _FileHelper val)
: Bool val
```
#### Parameters

*   that: [_FileHelper](files-_FileHelper) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: _FileHelper val)
: Bool val
```
#### Parameters

*   that: [_FileHelper](files-_FileHelper) val

#### Returns

* [Bool](builtin-Bool) val

---

