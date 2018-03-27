# TCPConnectAuth

```pony
primitive val TCPConnectAuth
```

## Constructors

### create

```pony
new val create(
  from: (AmbientAuth val | NetAuth val | TCPAuth val))
: TCPConnectAuth val^
```
#### Parameters

*   from: ([AmbientAuth](builtin-AmbientAuth) val | [NetAuth](net-NetAuth) val | [TCPAuth](net-TCPAuth) val)

#### Returns

* [TCPConnectAuth](net-TCPConnectAuth) val^

---

## Public Functions

### eq

```pony
fun box eq(
  that: TCPConnectAuth val)
: Bool val
```
#### Parameters

*   that: [TCPConnectAuth](net-TCPConnectAuth) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: TCPConnectAuth val)
: Bool val
```
#### Parameters

*   that: [TCPConnectAuth](net-TCPConnectAuth) val

#### Returns

* [Bool](builtin-Bool) val

---

