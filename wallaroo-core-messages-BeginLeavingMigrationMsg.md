# BeginLeavingMigrationMsg

```pony
class val BeginLeavingMigrationMsg is
  ChannelMsg val
```

#### Implements

* [ChannelMsg](wallaroo-core-messages-ChannelMsg) val

---

## Constructors

### create

```pony
new val create(
  remaining_workers': Array[String val] val,
  leaving_workers': Array[String val] val)
: BeginLeavingMigrationMsg val^
```
#### Parameters

*   remaining_workers': [Array](builtin-Array)\[[String](builtin-String) val\] val
*   leaving_workers': [Array](builtin-Array)\[[String](builtin-String) val\] val

#### Returns

* [BeginLeavingMigrationMsg](wallaroo-core-messages-BeginLeavingMigrationMsg) val^

---

## Public fields

* let remaining_workers: [Array](builtin-Array)\[[String](builtin-String) val\] val

---

* let leaving_workers: [Array](builtin-Array)\[[String](builtin-String) val\] val

---

