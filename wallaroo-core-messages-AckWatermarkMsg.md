# AckWatermarkMsg

```pony
class val AckWatermarkMsg is
  ChannelMsg val
```

#### Implements

* [ChannelMsg](wallaroo-core-messages-ChannelMsg) val

---

## Constructors

### create

```pony
new val create(
  sender_name': String val,
  sender_step_id': U128 val,
  seq_id': U64 val)
: AckWatermarkMsg val^
```
#### Parameters

*   sender_name': [String](builtin-String) val
*   sender_step_id': [U128](builtin-U128) val
*   seq_id': [U64](builtin-U64) val

#### Returns

* [AckWatermarkMsg](wallaroo-core-messages-AckWatermarkMsg) val^

---

## Public fields

* let sender_name: [String](builtin-String) val

---

* let sender_step_id: [U128](builtin-U128) val

---

* let seq_id: [U64](builtin-U64) val

---

