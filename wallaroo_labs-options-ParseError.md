# ParseError

```pony
interface ref ParseError
```

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

