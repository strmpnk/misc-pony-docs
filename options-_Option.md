# _Option

```pony
class ref _Option
```

## Constructors

### create

```pony
new ref create(
  long': String val,
  short': (String val | None val),
  arg': (None val | StringArgument val | I64Argument val | 
    F64Argument val),
  mode': (Required val | Optional val))
: _Option ref^
```
#### Parameters

*   long': [String](builtin-String) val
*   short': ([String](builtin-String) val | [None](builtin-None) val)
*   arg': ([None](builtin-None) val | [StringArgument](options-StringArgument) val | [I64Argument](options-I64Argument) val | 
    [F64Argument](options-F64Argument) val)
*   mode': ([Required](options-Required) val | [Optional](options-Optional) val)

#### Returns

* [_Option](options-_Option) ref^

---

## Public fields

* let long: [String](builtin-String) val

---

* let short: ([String](builtin-String) val | [None](builtin-None) val)

---

* let arg: ([None](builtin-None) val | [StringArgument](options-StringArgument) val | [I64Argument](options-I64Argument) val | 
    [F64Argument](options-F64Argument) val)

---

* let mode: ([Required](options-Required) val | [Optional](options-Optional) val)

---

## Public Functions

### matches

```pony
fun box matches(
  name: String box,
  shortmatch: Bool val)
: Bool val
```
#### Parameters

*   name: [String](builtin-String) box
*   shortmatch: [Bool](builtin-Bool) val

#### Returns

* [Bool](builtin-Bool) val

---

### has_argument

```pony
fun box has_argument()
: Bool val
```

#### Returns

* [Bool](builtin-Bool) val

---

### requires_argument

```pony
fun box requires_argument()
: Bool val
```

#### Returns

* [Bool](builtin-Bool) val

---

### accepts

```pony
fun box accepts(
  argument: String box)
: Bool val
```
#### Parameters

*   argument: [String](builtin-String) box

#### Returns

* [Bool](builtin-Bool) val

---

