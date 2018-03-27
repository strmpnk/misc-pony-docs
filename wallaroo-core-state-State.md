# State

```pony
trait ref State
```

## Public Functions

### write_log_entry

```pony
fun box write_log_entry(
  out_writer: Writer ref,
  auth: AmbientAuth val)
: None val
```
#### Parameters

*   out_writer: [Writer](buffered-Writer) ref
*   auth: [AmbientAuth](builtin-AmbientAuth) val

#### Returns

* [None](builtin-None) val

---

### read_log_entry

```pony
fun box read_log_entry(
  in_reader: Reader ref,
  auth: AmbientAuth val)
: State ref ?
```
#### Parameters

*   in_reader: [Reader](buffered-Reader) ref
*   auth: [AmbientAuth](builtin-AmbientAuth) val

#### Returns

* [State](wallaroo-core-state-State) ref ?

---

