# StatusOK

```pony
primitive val StatusOK is
  Status val
```

#### Implements

* [Status](net-http-Status) val

---

## Constructors

### create

```pony
new val create()
: StatusOK val^
```

#### Returns

* [StatusOK](net-http-StatusOK) val^

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
  that: StatusOK val)
: Bool val
```
#### Parameters

*   that: [StatusOK](net-http-StatusOK) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: StatusOK val)
: Bool val
```
#### Parameters

*   that: [StatusOK](net-http-StatusOK) val

#### Returns

* [Bool](builtin-Bool) val

---

