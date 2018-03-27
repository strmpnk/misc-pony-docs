# TCPAuth

```pony
primitive val TCPAuth
```

## Constructors

### create

```pony
new val create(
  from: (AmbientAuth val | NetAuth val))
: TCPAuth val^
```
#### Parameters

*   from: ([AmbientAuth](builtin-AmbientAuth) val | [NetAuth](net-NetAuth) val)

#### Returns

* [TCPAuth](net-TCPAuth) val^

---

## Public Functions

### eq

```pony
fun box eq(
  that: TCPAuth val)
: Bool val
```
#### Parameters

*   that: [TCPAuth](net-TCPAuth) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: TCPAuth val)
: Bool val
```
#### Parameters

*   that: [TCPAuth](net-TCPAuth) val

#### Returns

* [Bool](builtin-Bool) val

---

