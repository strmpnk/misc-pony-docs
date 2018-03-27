# StatusFound

```pony
primitive val StatusFound is
  Status val
```

#### Implements

* [Status](net-http-Status) val

---

## Constructors

### create

```pony
new val create()
: StatusFound val^
```

#### Returns

* [StatusFound](net-http-StatusFound) val^

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
  that: StatusFound val)
: Bool val
```
#### Parameters

*   that: [StatusFound](net-http-StatusFound) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: StatusFound val)
: Bool val
```
#### Parameters

*   that: [StatusFound](net-http-StatusFound) val

#### Returns

* [Bool](builtin-Bool) val

---

