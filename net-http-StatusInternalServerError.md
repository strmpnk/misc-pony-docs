# StatusInternalServerError

```pony
primitive val StatusInternalServerError is
  Status val
```

#### Implements

* [Status](net-http-Status) val

---

## Constructors

### create

```pony
new val create()
: StatusInternalServerError val^
```

#### Returns

* [StatusInternalServerError](net-http-StatusInternalServerError) val^

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
  that: StatusInternalServerError val)
: Bool val
```
#### Parameters

*   that: [StatusInternalServerError](net-http-StatusInternalServerError) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: StatusInternalServerError val)
: Bool val
```
#### Parameters

*   that: [StatusInternalServerError](net-http-StatusInternalServerError) val

#### Returns

* [Bool](builtin-Bool) val

---

