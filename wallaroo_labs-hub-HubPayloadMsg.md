# HubPayloadMsg

```pony
primitive val HubPayloadMsg is
  HubProtocolMsg val
```

#### Implements

* [HubProtocolMsg](wallaroo_labs-hub-HubProtocolMsg) val

---

## Constructors

### create

```pony
new val create()
: HubPayloadMsg val^
```

#### Returns

* [HubPayloadMsg](wallaroo_labs-hub-HubPayloadMsg) val^

---

## Public Functions

### apply

```pony
fun box apply(
  data: Array[U8 val] val)
: HubProtocolMsg val
```
#### Parameters

*   data: [Array](builtin-Array)\[[U8](builtin-U8) val\] val

#### Returns

* [HubProtocolMsg](wallaroo_labs-hub-HubProtocolMsg) val

---

### eq

```pony
fun box eq(
  that: HubPayloadMsg val)
: Bool val
```
#### Parameters

*   that: [HubPayloadMsg](wallaroo_labs-hub-HubPayloadMsg) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: HubPayloadMsg val)
: Bool val
```
#### Parameters

*   that: [HubPayloadMsg](wallaroo_labs-hub-HubPayloadMsg) val

#### Returns

* [Bool](builtin-Bool) val

---

