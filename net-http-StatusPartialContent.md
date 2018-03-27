# StatusPartialContent

```pony
primitive val StatusPartialContent is
  Status val
```

#### Implements

* [Status](net-http-Status) val

---

## Constructors

### create

```pony
new val create()
: StatusPartialContent val^
```

#### Returns

* [StatusPartialContent](net-http-StatusPartialContent) val^

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
  that: StatusPartialContent val)
: Bool val
```
#### Parameters

*   that: [StatusPartialContent](net-http-StatusPartialContent) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: StatusPartialContent val)
: Bool val
```
#### Parameters

*   that: [StatusPartialContent](net-http-StatusPartialContent) val

#### Returns

* [Bool](builtin-Bool) val

---

