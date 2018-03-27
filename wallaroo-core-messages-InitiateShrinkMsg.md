# InitiateShrinkMsg

```pony
class val InitiateShrinkMsg is
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
: InitiateShrinkMsg val^
```
#### Parameters

*   remaining_workers': [Array](builtin-Array)\[[String](builtin-String) val\] val
*   leaving_workers': [Array](builtin-Array)\[[String](builtin-String) val\] val

#### Returns

* [InitiateShrinkMsg](wallaroo-core-messages-InitiateShrinkMsg) val^

---

## Public fields

* let remaining_workers: [Array](builtin-Array)\[[String](builtin-String) val\] val

---

* let leaving_workers: [Array](builtin-Array)\[[String](builtin-String) val\] val

---

