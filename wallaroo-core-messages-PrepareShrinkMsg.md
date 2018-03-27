# PrepareShrinkMsg

```pony
class val PrepareShrinkMsg is
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
: PrepareShrinkMsg val^
```
#### Parameters

*   remaining_workers': [Array](builtin-Array)\[[String](builtin-String) val\] val
*   leaving_workers': [Array](builtin-Array)\[[String](builtin-String) val\] val

#### Returns

* [PrepareShrinkMsg](wallaroo-core-messages-PrepareShrinkMsg) val^

---

## Public fields

* let remaining_workers: [Array](builtin-Array)\[[String](builtin-String) val\] val

---

* let leaving_workers: [Array](builtin-Array)\[[String](builtin-String) val\] val

---

