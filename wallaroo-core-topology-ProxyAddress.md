# ProxyAddress

```pony
class val ProxyAddress
```

## Constructors

### create

```pony
new val create(
  w: String val,
  s_id: U128 val)
: ProxyAddress val^
```
#### Parameters

*   w: [String](builtin-String) val
*   s_id: [U128](builtin-U128) val

#### Returns

* [ProxyAddress](wallaroo-core-topology-ProxyAddress) val^

---

## Public fields

* let worker: [String](builtin-String) val

---

* let step_id: [U128](builtin-U128) val

---

## Public Functions

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
  that: ProxyAddress val)
: Bool val
```
#### Parameters

*   that: [ProxyAddress](wallaroo-core-topology-ProxyAddress) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: ProxyAddress val)
: Bool val
```
#### Parameters

*   that: [ProxyAddress](wallaroo-core-topology-ProxyAddress) val

#### Returns

* [Bool](builtin-Bool) val

---

