# StatusBadRequest

```pony
primitive val StatusBadRequest is
  Status val
```

#### Implements

* [Status](net-http-Status) val

---

## Constructors

### create

```pony
new val create()
: StatusBadRequest val^
```

#### Returns

* [StatusBadRequest](net-http-StatusBadRequest) val^

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
  that: StatusBadRequest val)
: Bool val
```
#### Parameters

*   that: [StatusBadRequest](net-http-StatusBadRequest) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: StatusBadRequest val)
: Bool val
```
#### Parameters

*   that: [StatusBadRequest](net-http-StatusBadRequest) val

#### Returns

* [Bool](builtin-Bool) val

---

