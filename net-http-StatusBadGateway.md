# StatusBadGateway

```pony
primitive val StatusBadGateway is
  Status val
```

#### Implements

* [Status](net-http-Status) val

---

## Constructors

### create

```pony
new val create()
: StatusBadGateway val^
```

#### Returns

* [StatusBadGateway](net-http-StatusBadGateway) val^

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
  that: StatusBadGateway val)
: Bool val
```
#### Parameters

*   that: [StatusBadGateway](net-http-StatusBadGateway) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: StatusBadGateway val)
: Bool val
```
#### Parameters

*   that: [StatusBadGateway](net-http-StatusBadGateway) val

#### Returns

* [Bool](builtin-Bool) val

---

