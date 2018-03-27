# FileStream

Asynchronous access to a File object. Wraps file operations print, write,
printv and writev. The File will be disposed through File._final.


```pony
actor tag FileStream is
  OutStream tag
```

#### Implements

* [OutStream](builtin-OutStream) tag

---

## Constructors

### create

```pony
new tag create(
  file: File iso)
: FileStream tag^
```
#### Parameters

*   file: [File](files-File) iso

#### Returns

* [FileStream](files-FileStream) tag^

---

## Public Behaviours

### print

Print some bytes and insert a newline afterwards.


```pony
be print(
  data: (String val | Array[U8 val] val))
```
#### Parameters

*   data: ([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)

---

### write

Print some bytes without inserting a newline afterwards.


```pony
be write(
  data: (String val | Array[U8 val] val))
```
#### Parameters

*   data: ([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)

---

### printv

Print an iterable collection of ByteSeqs.


```pony
be printv(
  data: ByteSeqIter val)
```
#### Parameters

*   data: [ByteSeqIter](builtin-ByteSeqIter) val

---

### writev

Write an iterable collection of ByteSeqs.


```pony
be writev(
  data: ByteSeqIter val)
```
#### Parameters

*   data: [ByteSeqIter](builtin-ByteSeqIter) val

---

