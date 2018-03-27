# File

Operations on a file.


```pony
class ref File
```

## Constructors

### create

```pony
new ref create(
  from: FilePath val)
: File ref^
```
#### Parameters

*   from: [FilePath](files-FilePath) val

#### Returns

* [File](files-File) ref^

---

### open

```pony
new ref open(
  from: FilePath val)
: File ref^
```
#### Parameters

*   from: [FilePath](files-FilePath) val

#### Returns

* [File](files-File) ref^

---

### _descriptor

```pony
new ref _descriptor(
  fd: I32 val,
  from: FilePath val)
: File ref^ ?
```
#### Parameters

*   fd: [I32](builtin-I32) val
*   from: [FilePath](files-FilePath) val

#### Returns

* [File](files-File) ref^ ?

---

## Public fields

* let path: [FilePath](files-FilePath) val

---

* let writeable: [Bool](builtin-Bool) val

---

## Public Functions

### errno

Returns the last error code set for this File


```pony
fun box errno()
: (FileOK val | FileError val | FileEOF val | 
    FileBadFileNumber val | FileExists val | FilePermissionDenied val)
```

#### Returns

* ([FileOK](files-FileOK) val | [FileError](files-FileError) val | [FileEOF](files-FileEOF) val | 
    [FileBadFileNumber](files-FileBadFileNumber) val | [FileExists](files-FileExists) val | [FilePermissionDenied](files-FilePermissionDenied) val)

---

### clear_errno

Clears the last error code set for this File.
Clears the error indicator for the stream.


```pony
fun ref clear_errno()
: None val
```

#### Returns

* [None](builtin-None) val

---

### valid

Returns true if the file is currently open.


```pony
fun box valid()
: Bool val
```

#### Returns

* [Bool](builtin-Bool) val

---

### line

Returns a line as a String. The newline is not included in the string. If
there is no more data, this raises an error. If there is a file error,
this raises an error.


```pony
fun ref line()
: String iso^ ?
```

#### Returns

* [String](builtin-String) iso^ ?

---

### read

Returns up to len bytes.


```pony
fun ref read(
  len: USize val)
: Array[U8 val] iso^
```
#### Parameters

*   len: [USize](builtin-USize) val

#### Returns

* [Array](builtin-Array)\[[U8](builtin-U8) val\] iso^

---

### read_string

Returns up to len bytes. The resulting string may have internal null
characters.


```pony
fun ref read_string(
  len: USize val)
: String iso^
```
#### Parameters

*   len: [USize](builtin-USize) val

#### Returns

* [String](builtin-String) iso^

---

### print

Same as write, buts adds a newline.


```pony
fun ref print(
  data: (String box | Array[U8 val] box))
: Bool val
```
#### Parameters

*   data: ([String](builtin-String) box | [Array](builtin-Array)\[[U8](builtin-U8) val\] box)

#### Returns

* [Bool](builtin-Bool) val

---

### printv

Print an iterable collection of ByteSeqs.


```pony
fun ref printv(
  data: ByteSeqIter box)
: Bool val
```
#### Parameters

*   data: [ByteSeqIter](builtin-ByteSeqIter) box

#### Returns

* [Bool](builtin-Bool) val

---

### write

Returns false if the file wasn't opened with write permission.
Returns false and closes the file if not all the bytes were written.


```pony
fun ref write(
  data: (String box | Array[U8 val] box))
: Bool val
```
#### Parameters

*   data: ([String](builtin-String) box | [Array](builtin-Array)\[[U8](builtin-U8) val\] box)

#### Returns

* [Bool](builtin-Bool) val

---

### writev

Write an iterable collection of ByteSeqs.


```pony
fun ref writev(
  data: ByteSeqIter box)
: Bool val
```
#### Parameters

*   data: [ByteSeqIter](builtin-ByteSeqIter) box

#### Returns

* [Bool](builtin-Bool) val

---

### queue

Queue data to be written
NOTE: Queue'd data will always be written before normal print/write
requested data


```pony
fun ref queue(
  data: (String box | Array[U8 val] box))
: None val
```
#### Parameters

*   data: ([String](builtin-String) box | [Array](builtin-Array)\[[U8](builtin-U8) val\] box)

#### Returns

* [None](builtin-None) val

---

### queuev

Queue an iterable collection of ByteSeqs to be written
NOTE: Queue'd data will always be written before normal print/write
requested data


```pony
fun ref queuev(
  data: ByteSeqIter box)
: None val
```
#### Parameters

*   data: [ByteSeqIter](builtin-ByteSeqIter) box

#### Returns

* [None](builtin-None) val

---

### flush

Flush any queued data


```pony
fun ref flush()
: Bool val
```

#### Returns

* [Bool](builtin-Bool) val

---

### position

Return the current cursor position in the file.


```pony
fun ref position()
: USize val
```

#### Returns

* [USize](builtin-USize) val

---

### size

Return the total length of the file.


```pony
fun ref size()
: USize val
```

#### Returns

* [USize](builtin-USize) val

---

### seek_start

Set the cursor position relative to the start of the file.


```pony
fun ref seek_start(
  offset: USize val)
: None val
```
#### Parameters

*   offset: [USize](builtin-USize) val

#### Returns

* [None](builtin-None) val

---

### seek_end

Set the cursor position relative to the end of the file.


```pony
fun ref seek_end(
  offset: USize val)
: None val
```
#### Parameters

*   offset: [USize](builtin-USize) val

#### Returns

* [None](builtin-None) val

---

### seek

Move the cursor position.


```pony
fun ref seek(
  offset: ISize val)
: None val
```
#### Parameters

*   offset: [ISize](builtin-ISize) val

#### Returns

* [None](builtin-None) val

---

### sync

Sync the file contents to physical storage.


```pony
fun ref sync()
: None val
```

#### Returns

* [None](builtin-None) val

---

### datasync

Sync the file contents to physical storage.


```pony
fun ref datasync()
: None val
```

#### Returns

* [None](builtin-None) val

---

### set_length

Change the file size. If it is made larger, the new contents are undefined.


```pony
fun ref set_length(
  len: USize val)
: Bool val
```
#### Parameters

*   len: [USize](builtin-USize) val

#### Returns

* [Bool](builtin-Bool) val

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

### lines

Returns an iterator for reading lines from the file.


```pony
fun ref lines()
: FileLines ref
```

#### Returns

* [FileLines](files-FileLines) ref

---

### dispose

Close the file. Future operations will do nothing.


```pony
fun ref dispose()
: None val
```

#### Returns

* [None](builtin-None) val

---

## Private Functions

### _get_error

Fetch errno from the OS.


```pony
fun box _get_error()
: (FileOK val | FileError val | FileEOF val | 
    FileBadFileNumber val | FileExists val | FilePermissionDenied val)
```

#### Returns

* ([FileOK](files-FileOK) val | [FileError](files-FileError) val | [FileEOF](files-FileEOF) val | 
    [FileBadFileNumber](files-FileBadFileNumber) val | [FileExists](files-FileExists) val | [FilePermissionDenied](files-FilePermissionDenied) val)

---

### _pending_writes

Write pending data.
Returns false if the file wasn't opened with write permission.
Returns false and closes the file and discards all pending data
if not all the bytes were written.
Returns true if it sent all pending data.


```pony
fun ref _pending_writes()
: Bool val
```

#### Returns

* [Bool](builtin-Bool) val

---

### _write_to_disk

Write pending data.
Returns false if the file wasn't opened with write permission.
Returns raises error if not all the bytes were written.
Returns true if it sent all pending data.
Returns num_processed and new pending_total also.


```pony
fun box _write_to_disk()
: (Bool val , USize val , USize val) ?
```

#### Returns

* ([Bool](builtin-Bool) val , [USize](builtin-USize) val , [USize](builtin-USize) val) ?

---

### _seek

Move the cursor position.


```pony
fun ref _seek(
  offset: I64 val,
  base: I32 val)
: None val
```
#### Parameters

*   offset: [I64](builtin-I64) val
*   base: [I32](builtin-I32) val

#### Returns

* [None](builtin-None) val

---

### _final

Close the file.


```pony
fun box _final()
: None val
```

#### Returns

* [None](builtin-None) val

---

