# WalkHandler

A handler for `FilePath.walk`.


```pony
interface ref WalkHandler
```

## Public Functions

### apply

```pony
fun ref apply(
  dir_path: FilePath val,
  dir_entries: Array[String val] ref)
: None val
```
#### Parameters

*   dir_path: [FilePath](files-FilePath) val
*   dir_entries: [Array](builtin-Array)\[[String](builtin-String) val\] ref

#### Returns

* [None](builtin-None) val

---

