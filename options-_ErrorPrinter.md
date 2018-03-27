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

*   matches: [Array](builtin-Array)\[[_Option](options-_Option) ref\] ref

#### Returns

* [_ErrorPrinter](options-_ErrorPrinter) ref^

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

* [_ErrorPrinter](options-_ErrorPrinter) ref^

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
*   option: [_Option](options-_Option) ref

#### Returns

* [_ErrorPrinter](options-_ErrorPrinter) ref^

---

### _missing

```pony
new ref _missing(
  option: _Option ref)
: _ErrorPrinter ref^
```
#### Parameters

*   option: [_Option](options-_Option) ref

#### Returns

* [_ErrorPrinter](options-_ErrorPrinter) ref^

---

## Public Functions

### reason

```pony
fun box reason()
: (UnrecognisedOption val | MissingArgument val | InvalidArgument val | 
    AmbiguousMatch val)
```

#### Returns

* ([UnrecognisedOption](options-UnrecognisedOption) val | [MissingArgument](options-MissingArgument) val | [InvalidArgument](options-InvalidArgument) val | 
    [AmbiguousMatch](options-AmbiguousMatch) val)

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

