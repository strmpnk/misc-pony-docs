# DNSAuth

```pony
primitive val DNSAuth
```

## Constructors

### create

```pony
new val create(
  from: (AmbientAuth val | NetAuth val))
: DNSAuth val^
```
#### Parameters

*   from: ([AmbientAuth](builtin-AmbientAuth) val | [NetAuth](net-NetAuth) val)

#### Returns

* [DNSAuth](net-DNSAuth) val^

---

## Public Functions

### eq

```pony
fun box eq(
  that: DNSAuth val)
: Bool val
```
#### Parameters

*   that: [DNSAuth](net-DNSAuth) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: DNSAuth val)
: Bool val
```
#### Parameters

*   that: [DNSAuth](net-DNSAuth) val

#### Returns

* [Bool](builtin-Bool) val

---

