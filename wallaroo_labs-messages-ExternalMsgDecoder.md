# ExternalMsgDecoder

```pony
primitive val ExternalMsgDecoder
```

## Constructors

### create

```pony
new val create()
: ExternalMsgDecoder val^
```

#### Returns

* [ExternalMsgDecoder](wallaroo_labs-messages-ExternalMsgDecoder) val^

---

## Public Functions

### apply

Decode an ExternalMsg that was been encoded by ExternalMsgEncoder.

NOTE: ExternalMsgEncoder adds a 4 byte header that describes
      the length of the serialized message.  This decoder function
      assumes that the caller has stripped off that header.
      For example, Wallaroo assumes that the Pony TCP actor has
      already removed the header bytes as part of the
      ExternalChannelConnectNotifier's operation.


```pony
fun box apply(
  data: Array[U8 val] val)
: ExternalMsg val ?
```
#### Parameters

*   data: [Array](builtin-Array)\[[U8](builtin-U8) val\] val

#### Returns

* [ExternalMsg](wallaroo_labs-messages-ExternalMsg) val ?

---

### eq

```pony
fun box eq(
  that: ExternalMsgDecoder val)
: Bool val
```
#### Parameters

*   that: [ExternalMsgDecoder](wallaroo_labs-messages-ExternalMsgDecoder) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: ExternalMsgDecoder val)
: Bool val
```
#### Parameters

*   that: [ExternalMsgDecoder](wallaroo_labs-messages-ExternalMsgDecoder) val

#### Returns

* [Bool](builtin-Bool) val

---

## Private Functions

### _decode

```pony
fun box _decode(
  data: Array[U8 val] val)
: (U16 val , String val) ?
```
#### Parameters

*   data: [Array](builtin-Array)\[[U8](builtin-U8) val\] val

#### Returns

* ([U16](builtin-U16) val , [String](builtin-String) val) ?

---

