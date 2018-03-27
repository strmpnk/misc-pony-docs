# StatusPaymentRequired

```pony
primitive val StatusPaymentRequired is
  Status val
```

#### Implements

* [Status](net-http-Status) val

---

## Constructors

### create

```pony
new val create()
: StatusPaymentRequired val^
```

#### Returns

* [StatusPaymentRequired](net-http-StatusPaymentRequired) val^

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
  that: StatusPaymentRequired val)
: Bool val
```
#### Parameters

*   that: [StatusPaymentRequired](net-http-StatusPaymentRequired) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: StatusPaymentRequired val)
: Bool val
```
#### Parameters

*   that: [StatusPaymentRequired](net-http-StatusPaymentRequired) val

#### Returns

* [Bool](builtin-Bool) val

---

