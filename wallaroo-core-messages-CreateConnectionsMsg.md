# CreateConnectionsMsg

```pony
class val CreateConnectionsMsg is
  ChannelMsg val
```

#### Implements

* [ChannelMsg](wallaroo-core-messages-ChannelMsg) val

---

## Constructors

### create

```pony
new val create(
  c_addrs: HashMap[String val, (String val , String val), HashEq[String val] val] val,
  d_addrs: HashMap[String val, (String val , String val), HashEq[String val] val] val)
: CreateConnectionsMsg val^
```
#### Parameters

*   c_addrs: [HashMap](collections-HashMap)\[[String](builtin-String) val, ([String](builtin-String) val , [String](builtin-String) val), [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val
*   d_addrs: [HashMap](collections-HashMap)\[[String](builtin-String) val, ([String](builtin-String) val , [String](builtin-String) val), [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val

#### Returns

* [CreateConnectionsMsg](wallaroo-core-messages-CreateConnectionsMsg) val^

---

## Public fields

* let control_addrs: [HashMap](collections-HashMap)\[[String](builtin-String) val, ([String](builtin-String) val , [String](builtin-String) val), [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val

---

* let data_addrs: [HashMap](collections-HashMap)\[[String](builtin-String) val, ([String](builtin-String) val , [String](builtin-String) val), [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val

---

