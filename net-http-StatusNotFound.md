# StatusNotFound

```pony
primitive val StatusNotFound is
  Status val
```

#### Implements

* [Status](net-http-Status) val

---

## Constructors

### create

```pony
new val create()
: StatusNotFound val^
```

#### Returns

* [StatusNotFound](net-http-StatusNotFound) val^

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
  that: StatusNotFound val)
: Bool val
```
#### Parameters

*   that: [StatusNotFound](net-http-StatusNotFound) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: StatusNotFound val)
: Bool val
```
#### Parameters

*   that: [StatusNotFound](net-http-StatusNotFound) val

#### Returns

* [Bool](builtin-Bool) val

---

