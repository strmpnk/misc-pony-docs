# StatusConflict

```pony
primitive val StatusConflict is
  Status val
```

#### Implements

* [Status](net-http-Status) val

---

## Constructors

### create

```pony
new val create()
: StatusConflict val^
```

#### Returns

* [StatusConflict](net-http-StatusConflict) val^

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
  that: StatusConflict val)
: Bool val
```
#### Parameters

*   that: [StatusConflict](net-http-StatusConflict) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: StatusConflict val)
: Bool val
```
#### Parameters

*   that: [StatusConflict](net-http-StatusConflict) val

#### Returns

* [Bool](builtin-Bool) val

---

