# FileBackend

```pony
class ref FileBackend is
  Backend ref
```

#### Implements

* [Backend](wallaroo-ent-recovery-Backend) ref

---

## Constructors

### create

```pony
new ref create(
  filepath: FilePath val,
  event_log: EventLog tag)
: FileBackend ref^
```
#### Parameters

*   filepath: [FilePath](files-FilePath) val
*   event_log: [EventLog](wallaroo-ent-recovery-EventLog) tag

#### Returns

* [FileBackend](wallaroo-ent-recovery-FileBackend) ref^

---

## Public Functions

### dispose

```pony
fun ref dispose()
: None val
```

#### Returns

* [None](builtin-None) val

---

### bytes_written

```pony
fun box bytes_written()
: USize val
```

#### Returns

* [USize](builtin-USize) val

---

### start_log_replay

```pony
fun ref start_log_replay()
: None val
```

#### Returns

* [None](builtin-None) val

---

### write

```pony
fun ref write()
: USize val ?
```

#### Returns

* [USize](builtin-USize) val ?

---

### encode_entry

```pony
fun ref encode_entry(
  entry: (Bool val , U128 val , U128 val , 
    (Array[U32 val] val | None val) , U64 val , U64 val , 
    Array[(String val | Array[U8 val] val)] val))
: None val
```
#### Parameters

*   entry: ([Bool](builtin-Bool) val , [U128](builtin-U128) val , [U128](builtin-U128) val , 
    ([Array](builtin-Array)\[[U32](builtin-U32) val\] val | [None](builtin-None) val) , [U64](builtin-U64) val , [U64](builtin-U64) val , 
    [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val)

#### Returns

* [None](builtin-None) val

---

### sync

```pony
fun ref sync()
: None val ?
```

#### Returns

* [None](builtin-None) val ?

---

### datasync

```pony
fun ref datasync()
: None val ?
```

#### Returns

* [None](builtin-None) val ?

---

