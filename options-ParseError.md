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

