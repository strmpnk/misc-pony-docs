# DataConnectMsg

```pony
class val DataConnectMsg is
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
  sender_boundary_id': U128 val)
: DataConnectMsg val^
```
#### Parameters

*   sender_name': [String](builtin-String) val
*   sender_boundary_id': [U128](builtin-U128) val

#### Returns

* [DataConnectMsg](wallaroo-core-messages-DataConnectMsg) val^

---

## Public fields

* let sender_name: [String](builtin-String) val

---

* let sender_boundary_id: [U128](builtin-U128) val

---

