# StatusPreconditionFailed

```pony
primitive val StatusPreconditionFailed is
  Status val
```

#### Implements

* [Status](net-http-Status) val

---

## Constructors

### create

```pony
new val create()
: StatusPreconditionFailed val^
```

#### Returns

* [StatusPreconditionFailed](net-http-StatusPreconditionFailed) val^

---

## Public Functions

### apply

```pony
fun box apply()
: U16 val
```

#### Returns

* [U16](builtin-U16) val

---

### string

```pony
fun box string()
: String val
```

#### Returns

* [String](builtin-String) val

---

### eq

```pony
fun box eq(
  that: StatusPreconditionFailed val)
: Bool val
```
#### Parameters

*   that: [StatusPreconditionFailed](net-http-StatusPreconditionFailed) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: StatusPreconditionFailed val)
: Bool val
```
#### Parameters

*   that: [StatusPreconditionFailed](net-http-StatusPreconditionFailed) val

#### Returns

* [Bool](builtin-Bool) val

---

