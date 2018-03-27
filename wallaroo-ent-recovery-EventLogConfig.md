# EventLogConfig

```pony
class val EventLogConfig
```

## Constructors

### create

```pony
new val create(
  log_dir': (FilePath val | AmbientAuth val | None val) = seq,
  filename': (String val | None val) = seq,
  logging_batch_size': USize val = seq,
  backend_file_length': (USize val | None val) = seq,
  log_rotation': Bool val = seq,
  suffix': String val = seq)
: EventLogConfig val^
```
#### Parameters

*   log_dir': ([FilePath](files-FilePath) val | [AmbientAuth](builtin-AmbientAuth) val | [None](builtin-None) val) = seq
*   filename': ([String](builtin-String) val | [None](builtin-None) val) = seq
*   logging_batch_size': [USize](builtin-USize) val = seq
*   backend_file_length': ([USize](builtin-USize) val | [None](builtin-None) val) = seq
*   log_rotation': [Bool](builtin-Bool) val = seq
*   suffix': [String](builtin-String) val = seq

#### Returns

* [EventLogConfig](wallaroo-ent-recovery-EventLogConfig) val^

---

## Public fields

* let log_dir: ([FilePath](files-FilePath) val | [AmbientAuth](builtin-AmbientAuth) val | [None](builtin-None) val)

---

* let filename: ([String](builtin-String) val | [None](builtin-None) val)

---

* let logging_batch_size: [USize](builtin-USize) val

---

* let backend_file_length: ([USize](builtin-USize) val | [None](builtin-None) val)

---

* let log_rotation: [Bool](builtin-Bool) val

---

* let suffix: [String](builtin-String) val

---

