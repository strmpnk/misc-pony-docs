# StateChange\[S: [State](wallaroo-core-state-State) ref\]

```pony
trait ref StateChange[S: State ref]
```

## Public Functions

### name

```pony
fun box name()
: String val
```

#### Returns

* [String](builtin-String) val

---

### id

```pony
fun box id()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### apply

```pony
fun box apply(
  state: S)
: None val
```
#### Parameters

*   state: S

#### Returns

* [None](builtin-None) val

---

### write_log_entry

```pony
fun box write_log_entry(
  out_writer: Writer ref)
: None val
```
#### Parameters

*   out_writer: [Writer](buffered-Writer) ref

#### Returns

* [None](builtin-None) val

---

### read_log_entry

```pony
fun ref read_log_entry(
  in_reader: Reader ref)
: None val ?
```
#### Parameters

*   in_reader: [Reader](buffered-Reader) ref

#### Returns

* [None](builtin-None) val ?

---

