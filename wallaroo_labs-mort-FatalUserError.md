# FatalUserError

An error was encountered due to bad input from the user in terms of startup
options or configuration. Exit and inform them of the problem.


```pony
primitive val FatalUserError
```

## Constructors

### create

```pony
new val create()
: FatalUserError val^
```

#### Returns

* [FatalUserError](wallaroo_labs-mort-FatalUserError) val^

---

## Public Functions

### apply

```pony
fun box apply(
  msg: String val)
: None val
```
#### Parameters

*   msg: [String](builtin-String) val

#### Returns

* [None](builtin-None) val

---

### eq

```pony
fun box eq(
  that: FatalUserError val)
: Bool val
```
#### Parameters

*   that: [FatalUserError](wallaroo_labs-mort-FatalUserError) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: FatalUserError val)
: Bool val
```
#### Parameters

*   that: [FatalUserError](wallaroo_labs-mort-FatalUserError) val

#### Returns

* [Bool](builtin-Bool) val

---

