# RotatingFileBackend

```pony
class ref RotatingFileBackend is
  Backend ref
```

#### Implements

* [Backend](wallaroo-ent-recovery-Backend) ref

---

## Constructors

### create

```pony
new ref create(
  base_dir: FilePath val,
  base_name: String val,
  suffix: String val = seq,
  event_log: EventLog tag,
  file_length: (USize val | None val))
: RotatingFileBackend ref^ ?
```
#### Parameters

*   base_dir: [FilePath](files-FilePath) val
*   base_name: [String](builtin-String) val
*   suffix: [String](builtin-String) val = seq
*   event_log: [EventLog](wallaroo-ent-recovery-EventLog) tag
*   file_length: ([USize](builtin-USize) val | [None](builtin-None) val)

#### Returns

* [RotatingFileBackend](wallaroo-ent-recovery-RotatingFileBackend) ref^ ?

---

## Public Functions

### bytes_written

```pony
fun box bytes_written()
: USize val
```

#### Returns

* [USize](builtin-USize) val

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

### rotate_file

```pony
fun ref rotate_file()
: None val ?
```

#### Returns

* [None](builtin-None) val ?

---

