# ReplayBoundaryCountMsg

```pony
class val ReplayBoundaryCountMsg is
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
  count: USize val)
: ReplayBoundaryCountMsg val^
```
#### Parameters

*   from: [String](builtin-String) val
*   count: [USize](builtin-USize) val

#### Returns

* [ReplayBoundaryCountMsg](wallaroo-core-messages-ReplayBoundaryCountMsg) val^

---

## Public fields

* let sender_name: [String](builtin-String) val

---

* let boundary_count: [USize](builtin-USize) val

---

