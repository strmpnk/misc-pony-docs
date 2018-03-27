# Options

```pony
class ref Options is
  Iterator[((String val , (None val | String val | I64 val | F64 val)) | ParseError ref | None val)] ref
```

#### Implements

* [Iterator](builtin-Iterator)\[(([String](builtin-String) val , ([None](builtin-None) val | [String](builtin-String) val | [I64](builtin-I64) val | [F64](builtin-F64) val)) | [ParseError](wallaroo_labs-options-ParseError) ref | [None](builtin-None) val)\] ref

---

## Constructors

### create

```pony
new ref create(
  args: Array[String val] box,
  fatal: Bool val = seq)
: Options ref^
```
#### Parameters

*   args: [Array](builtin-Array)\[[String](builtin-String) val\] box
*   fatal: [Bool](builtin-Bool) val = seq

#### Returns

* [Options](wallaroo_labs-options-Options) ref^

---

## Public Functions

### add

Adds a new named option to the parser configuration.


```pony
fun ref add(
  long: String val,
  short: (None val | String val) = seq,
  arg: (None val | StringArgument val | I64Argument val | 
    F64Argument val) = seq,
  mode: (Required val | Optional val) = seq)
: Options ref
```
#### Parameters

*   long: [String](builtin-String) val
*   short: ([None](builtin-None) val | [String](builtin-String) val) = seq
*   arg: ([None](builtin-None) val | [StringArgument](wallaroo_labs-options-StringArgument) val | [I64Argument](wallaroo_labs-options-I64Argument) val | 
    [F64Argument](wallaroo_labs-options-F64Argument) val) = seq
*   mode: ([Required](wallaroo_labs-options-Required) val | [Optional](wallaroo_labs-options-Optional) val) = seq

#### Returns

* [Options](wallaroo_labs-options-Options) ref

---

### remaining

Returns all unprocessed command line arguments. After parsing all options,
this will only include positional arguments, potentially unrecognised and
ambiguous options and invalid arguments.


```pony
fun ref remaining()
: Array[String val] val
```

#### Returns

* [Array](builtin-Array)\[[String](builtin-String) val\] val

---

### has_next

Parsing options is done if either an error occurs and fatal error reporting
is turned on, or if all command line arguments have been processed.


```pony
fun box has_next()
: Bool val
```

#### Returns

* [Bool](builtin-Bool) val

---

### next

Skips all positional arguments and attemps to match named options. Returns
a ParsedOption on success, a ParseError on error, or None if no named
options are found.


```pony
fun ref next()
: ((String val , (None val | String val | I64 val | 
    F64 val)) | ParseError ref | None val)
```

#### Returns

* (([String](builtin-String) val , ([None](builtin-None) val | [String](builtin-String) val | [I64](builtin-I64) val | 
    [F64](builtin-F64) val)) | [ParseError](wallaroo_labs-options-ParseError) ref | [None](builtin-None) val)

---

## Private Functions

### _strip

Strips accepted options from the copied array of command line arguments.


```pony
fun ref _strip(
  opt: _Option ref,
  matched: String ref,
  start: ISize val,
  finish: ISize val)
: None val
```
#### Parameters

*   opt: [_Option](wallaroo_labs-options-_Option) ref
*   matched: [String](builtin-String) ref
*   start: [ISize](builtin-ISize) val
*   finish: [ISize](builtin-ISize) val

#### Returns

* [None](builtin-None) val

---

### _select

Selects an option from the configuration depending on the current command
line argument.


```pony
fun ref _select(
  candidate: String ref,
  start: ISize val,
  offset: ISize val,
  finish: ISize val)
: (_Option ref | ParseError ref)
```
#### Parameters

*   candidate: [String](builtin-String) ref
*   start: [ISize](builtin-ISize) val
*   offset: [ISize](builtin-ISize) val
*   finish: [ISize](builtin-ISize) val

#### Returns

* ([_Option](wallaroo_labs-options-_Option) ref | [ParseError](wallaroo_labs-options-ParseError) ref)

---

### _skip

Skips all non-options. Returns true if a named option has been found, false
otherwise.


```pony
fun ref _skip()
: Bool val
```

#### Returns

* [Bool](builtin-Bool) val

---

### _verify

Verifies whether a parsed option from the command line is well-formed. That
is, checking whether required or optional arguments are supplied. Returns
a ParsedOption on success, a ParseError otherwise.


```pony
fun ref _verify(
  opt: _Option ref,
  combined: Bool val)
: ((String val , (None val | String val | I64 val | 
    F64 val)) | ParseError ref)
```
#### Parameters

*   opt: [_Option](wallaroo_labs-options-_Option) ref
*   combined: [Bool](builtin-Bool) val

#### Returns

* (([String](builtin-String) val , ([None](builtin-None) val | [String](builtin-String) val | [I64](builtin-I64) val | 
    [F64](builtin-F64) val)) | [ParseError](wallaroo_labs-options-ParseError) ref)

---

