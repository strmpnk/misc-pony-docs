# StatusCreated

```pony
primitive val StatusCreated is
  Status val
```

#### Implements

* [Status](net-http-Status) val

---

## Constructors

### create

```pony
new val create()
: StatusCreated val^
```

#### Returns

* [StatusCreated](net-http-StatusCreated) val^

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
  that: StatusCreated val)
: Bool val
```
#### Parameters

*   that: [StatusCreated](net-http-StatusCreated) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: StatusCreated val)
: Bool val
```
#### Parameters

*   that: [StatusCreated](net-http-StatusCreated) val

#### Returns

* [Bool](builtin-Bool) val

---

