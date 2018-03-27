# HubProtocolDecoder

```pony
primitive val HubProtocolDecoder
```

## Constructors

### create

```pony
new val create()
: HubProtocolDecoder val^
```

#### Returns

* [HubProtocolDecoder](wallaroo_labs-hub-HubProtocolDecoder) val^

---

## Public Functions

### apply

```pony
fun box apply(
  data: Array[U8 val] val)
: HubProtocolMsg val ?
```
#### Parameters

*   data: [Array](builtin-Array)\[[U8](builtin-U8) val\] val

#### Returns

* [HubProtocolMsg](wallaroo_labs-hub-HubProtocolMsg) val ?

---

### eq

```pony
fun box eq(
  that: HubProtocolDecoder val)
: Bool val
```
#### Parameters

*   that: [HubProtocolDecoder](wallaroo_labs-hub-HubProtocolDecoder) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: HubProtocolDecoder val)
: Bool val
```
#### Parameters

*   that: [HubProtocolDecoder](wallaroo_labs-hub-HubProtocolDecoder) val

#### Returns

* [Bool](builtin-Bool) val

---

## Private Functions

### _decode

```pony
fun box _decode(
  data: Array[U8 val] val)
: (U8 val , Array[U8 val] val) ?
```
#### Parameters

*   data: [Array](builtin-Array)\[[U8](builtin-U8) val\] val

#### Returns

* ([U8](builtin-U8) val , [Array](builtin-Array)\[[U8](builtin-U8) val\] val) ?

---

