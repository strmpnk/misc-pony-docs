# ReplayCompleteMsg

```pony
class val ReplayCompleteMsg is
  ChannelMsg val
```

#### Implements

* [ChannelMsg](wallaroo-core-messages-ChannelMsg) val

---

## Constructors

### create

```pony
new val create(
  from: String val,
  b_id: U128 val)
: ReplayCompleteMsg val^
```
#### Parameters

*   from: [String](builtin-String) val
*   b_id: [U128](builtin-U128) val

#### Returns

* [ReplayCompleteMsg](wallaroo-core-messages-ReplayCompleteMsg) val^

---

## Public fields

* let sender_name: [String](builtin-String) val

---

* let boundary_id: [U128](builtin-U128) val

---

