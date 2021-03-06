# StatusTooManyRequests

```pony
primitive val StatusTooManyRequests is
  Status val
```

#### Implements

* [Status](net-http-Status) val

---

## Constructors

### create

```pony
new val create()
: StatusTooManyRequests val^
```

#### Returns

* [StatusTooManyRequests](net-http-StatusTooManyRequests) val^

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
  that: StatusTooManyRequests val)
: Bool val
```
#### Parameters

*   that: [StatusTooManyRequests](net-http-StatusTooManyRequests) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: StatusTooManyRequests val)
: Bool val
```
#### Parameters

*   that: [StatusTooManyRequests](net-http-StatusTooManyRequests) val

#### Returns

* [Bool](builtin-Bool) val

---

