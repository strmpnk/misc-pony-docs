# StartNormalDataSendingMsg

```pony
class val StartNormalDataSendingMsg is
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
: StartNormalDataSendingMsg val^
```
#### Parameters

*   last_id_seen': [U64](builtin-U64) val

#### Returns

* [StartNormalDataSendingMsg](wallaroo-core-messages-StartNormalDataSendingMsg) val^

---

## Public fields

* let last_id_seen: [U64](builtin-U64) val

---

