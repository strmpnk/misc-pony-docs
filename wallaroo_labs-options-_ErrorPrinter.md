# _ErrorPrinter

```pony
class ref _ErrorPrinter
```

## Constructors

### _ambiguous

```pony
new ref _ambiguous(
  matches: Array[_Option ref] ref)
: _ErrorPrinter ref^
```
#### Parameters

*   matches: [Array](builtin-Array)\[[_Option](wallaroo_labs-options-_Option) ref\] ref

#### Returns

* [_ErrorPrinter](wallaroo_labs-options-_ErrorPrinter) ref^

---

### _unrecognised

```pony
new ref _unrecognised(
  option: String box)
: _ErrorPrinter ref^
```
#### Parameters

*   option: [String](builtin-String) box

#### Returns

* [_ErrorPrinter](wallaroo_labs-options-_ErrorPrinter) ref^

---

### _invalid

```pony
new ref _invalid(
  argument: String box,
  option: _Option ref)
: _ErrorPrinter ref^
```
#### Parameters

*   argument: [String](builtin-String) box
*   option: [_Option](wallaroo_labs-options-_Option) ref

#### Returns

* [_ErrorPrinter](wallaroo_labs-options-_ErrorPrinter) ref^

---

### _missing

```pony
new ref _missing(
  option: _Option ref)
: _ErrorPrinter ref^
```
#### Parameters

*   option: [_Option](wallaroo_labs-options-_Option) ref

#### Returns

* [_ErrorPrinter](wallaroo_labs-options-_ErrorPrinter) ref^

---

## Public Functions

### reason

```pony
fun box reason()
: (UnrecognisedOption val | MissingArgument val | InvalidArgument val | 
    AmbiguousMatch val)
```

#### Returns

* ([UnrecognisedOption](wallaroo_labs-options-UnrecognisedOption) val | [MissingArgument](wallaroo_labs-options-MissingArgument) val | [InvalidArgument](wallaroo_labs-options-InvalidArgument) val | 
    [AmbiguousMatch](wallaroo_labs-options-AmbiguousMatch) val)

---

### report

```pony
fun box report(
  out: OutStream tag)
: None val
```
#### Parameters

*   out: [OutStream](builtin-OutStream) tag

#### Returns

* [None](builtin-None) val

---

