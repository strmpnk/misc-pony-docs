# UDPAuth

```pony
primitive val UDPAuth
```

## Constructors

### create

```pony
new val create(
  from: (AmbientAuth val | NetAuth val))
: UDPAuth val^
```
#### Parameters

*   from: ([AmbientAuth](builtin-AmbientAuth) val | [NetAuth](net-NetAuth) val)

#### Returns

* [UDPAuth](net-UDPAuth) val^

---

## Public Functions

### eq

```pony
fun box eq(
  that: UDPAuth val)
: Bool val
```
#### Parameters

*   that: [UDPAuth](net-UDPAuth) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: UDPAuth val)
: Bool val
```
#### Parameters

*   that: [UDPAuth](net-UDPAuth) val

#### Returns

* [Bool](builtin-Bool) val

---

