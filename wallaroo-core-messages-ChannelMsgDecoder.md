# ChannelMsgDecoder

```pony
primitive val ChannelMsgDecoder
```

## Constructors

### create

```pony
new val create()
: ChannelMsgDecoder val^
```

#### Returns

* [ChannelMsgDecoder](wallaroo-core-messages-ChannelMsgDecoder) val^

---

## Public Functions

### apply

```pony
fun box apply(
  data: Array[U8 val] val,
  auth: AmbientAuth val)
: ChannelMsg val
```
#### Parameters

*   data: [Array](builtin-Array)\[[U8](builtin-U8) val\] val
*   auth: [AmbientAuth](builtin-AmbientAuth) val

#### Returns

* [ChannelMsg](wallaroo-core-messages-ChannelMsg) val

---

### eq

```pony
fun box eq(
  that: ChannelMsgDecoder val)
: Bool val
```
#### Parameters

*   that: [ChannelMsgDecoder](wallaroo-core-messages-ChannelMsgDecoder) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: ChannelMsgDecoder val)
: Bool val
```
#### Parameters

*   that: [ChannelMsgDecoder](wallaroo-core-messages-ChannelMsgDecoder) val

#### Returns

* [Bool](builtin-Bool) val

---

