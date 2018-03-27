# LastLogFilePath

```pony
primitive val LastLogFilePath
```

## Constructors

### create

```pony
new val create()
: LastLogFilePath val^
```

#### Returns

* [LastLogFilePath](wallaroo-ent-recovery-LastLogFilePath) val^

---

## Public Functions

### apply

```pony
fun box apply(
  base_name: String val,
  suffix: String val = seq,
  base_dir: FilePath val)
: FilePath val ?
```
#### Parameters

*   base_name: [String](builtin-String) val
*   suffix: [String](builtin-String) val = seq
*   base_dir: [FilePath](files-FilePath) val

#### Returns

* [FilePath](files-FilePath) val ?

---

### eq

```pony
fun box eq(
  that: LastLogFilePath val)
: Bool val
```
#### Parameters

*   that: [LastLogFilePath](wallaroo-ent-recovery-LastLogFilePath) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: LastLogFilePath val)
: Bool val
```
#### Parameters

*   that: [LastLogFilePath](wallaroo-ent-recovery-LastLogFilePath) val

#### Returns

* [Bool](builtin-Bool) val

---

