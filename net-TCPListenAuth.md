# TCPListenAuth

```pony
primitive val TCPListenAuth
```

## Constructors

### create

```pony
new val create(
  from: (AmbientAuth val | NetAuth val | TCPAuth val))
: TCPListenAuth val^
```
#### Parameters

*   from: ([AmbientAuth](builtin-AmbientAuth) val | [NetAuth](net-NetAuth) val | [TCPAuth](net-TCPAuth) val)

#### Returns

* [TCPListenAuth](net-TCPListenAuth) val^

---

## Public Functions

### eq

```pony
fun box eq(
  that: TCPListenAuth val)
: Bool val
```
#### Parameters

*   that: [TCPListenAuth](net-TCPListenAuth) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: TCPListenAuth val)
: Bool val
```
#### Parameters

*   that: [TCPListenAuth](net-TCPListenAuth) val

#### Returns

* [Bool](builtin-Bool) val

---

