# StatusExpectationFailed

```pony
primitive val StatusExpectationFailed is
  Status val
```

#### Implements

* [Status](net-http-Status) val

---

## Constructors

### create

```pony
new val create()
: StatusExpectationFailed val^
```

#### Returns

* [StatusExpectationFailed](net-http-StatusExpectationFailed) val^

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
  that: StatusExpectationFailed val)
: Bool val
```
#### Parameters

*   that: [StatusExpectationFailed](net-http-StatusExpectationFailed) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: StatusExpectationFailed val)
: Bool val
```
#### Parameters

*   that: [StatusExpectationFailed](net-http-StatusExpectationFailed) val

#### Returns

* [Bool](builtin-Bool) val

---

