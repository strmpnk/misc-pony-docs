# StatusUnauthorized

```pony
primitive val StatusUnauthorized is
  Status val
```

#### Implements

* [Status](net-http-Status) val

---

## Constructors

### create

```pony
new val create()
: StatusUnauthorized val^
```

#### Returns

* [StatusUnauthorized](net-http-StatusUnauthorized) val^

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
  that: StatusUnauthorized val)
: Bool val
```
#### Parameters

*   that: [StatusUnauthorized](net-http-StatusUnauthorized) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: StatusUnauthorized val)
: Bool val
```
#### Parameters

*   that: [StatusUnauthorized](net-http-StatusUnauthorized) val

#### Returns

* [Bool](builtin-Bool) val

---

