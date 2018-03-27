# StatusForbidden

```pony
primitive val StatusForbidden is
  Status val
```

#### Implements

* [Status](net-http-Status) val

---

## Constructors

### create

```pony
new val create()
: StatusForbidden val^
```

#### Returns

* [StatusForbidden](net-http-StatusForbidden) val^

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
  that: StatusForbidden val)
: Bool val
```
#### Parameters

*   that: [StatusForbidden](net-http-StatusForbidden) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: StatusForbidden val)
: Bool val
```
#### Parameters

*   that: [StatusForbidden](net-http-StatusForbidden) val

#### Returns

* [Bool](builtin-Bool) val

---

