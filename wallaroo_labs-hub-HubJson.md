# HubJson

```pony
primitive val HubJson
```

## Constructors

### create

```pony
new val create()
: HubJson val^
```

#### Returns

* [HubJson](wallaroo_labs-hub-HubJson) val^

---

## Public Functions

### connect

```pony
fun box connect()
: String val
```

#### Returns

* [String](builtin-String) val

---

### join

```pony
fun box join(
  topic: String val)
: String val
```
#### Parameters

*   topic: [String](builtin-String) val

#### Returns

* [String](builtin-String) val

---

### payload

```pony
fun box payload(
  event: String val,
  topic: String val,
  payload': JsonArray ref,
  pretty_print: Bool val = seq)
: String val
```
#### Parameters

*   event: [String](builtin-String) val
*   topic: [String](builtin-String) val
*   payload': [JsonArray](json-JsonArray) ref
*   pretty_print: [Bool](builtin-Bool) val = seq

#### Returns

* [String](builtin-String) val

---

### eq

```pony
fun box eq(
  that: HubJson val)
: Bool val
```
#### Parameters

*   that: [HubJson](wallaroo_labs-hub-HubJson) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: HubJson val)
: Bool val
```
#### Parameters

*   that: [HubJson](wallaroo_labs-hub-HubJson) val

#### Returns

* [Bool](builtin-Bool) val

---

