# AckDataConnectMsg

```pony
class val AckDataConnectMsg is
  ChannelMsg val
```

#### Implements

* [ChannelMsg](wallaroo-core-messages-ChannelMsg) val

---

## Constructors

### create

```pony
new val create(
  last_id_seen': U64 val)
: AckDataConnectMsg val^
```
#### Parameters

*   last_id_seen': [U64](builtin-U64) val

#### Returns

* [AckDataConnectMsg](wallaroo-core-messages-AckDataConnectMsg) val^

---

## Public fields

* let last_id_seen: [U64](builtin-U64) val

---

