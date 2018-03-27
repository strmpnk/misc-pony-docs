# FileLines

Iterate over the lines in a file.


```pony
class ref FileLines is
  Iterator[String val] ref
```

#### Implements

* [Iterator](builtin-Iterator)\[[String](builtin-String) val\] ref

---

## Constructors

### create

```pony
new ref create(
  file: File ref)
: FileLines ref^
```
#### Parameters

*   file: [File](files-File) ref

#### Returns

* [FileLines](files-FileLines) ref^

---

## Public Functions

### has_next

```pony
fun ref has_next()
: Bool val
```

#### Returns

* [Bool](builtin-Bool) val

---

### next

```pony
fun ref next()
: String val
```

#### Returns

* [String](builtin-String) val

---

