# SpinUpStepMsg

```pony
class val SpinUpStepMsg is
  ChannelMsg val
```

#### Implements

* [ChannelMsg](wallaroo-core-messages-ChannelMsg) val

---

## Constructors

### create

```pony
new val create(
  s_id: U64 val,
  s_builder: StepBuilder val)
: SpinUpStepMsg val^
```
#### Parameters

*   s_id: [U64](builtin-U64) val
*   s_builder: [StepBuilder](wallaroo-core-topology-StepBuilder) val

#### Returns

* [SpinUpStepMsg](wallaroo-core-messages-SpinUpStepMsg) val^

---

## Public fields

* let step_id: [U64](builtin-U64) val

---

* let step_builder: [StepBuilder](wallaroo-core-topology-StepBuilder) val

---

