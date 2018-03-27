# KeyedAnnounceNewStatefulStepMsg\[K: ([Hashable](collections-Hashable) val & [Equatable](builtin-Equatable)\[K\] val)\]

This message is sent to notify another worker that a new stateful step has
been created on this worker and that partition routers should be updated.


```pony
class val KeyedAnnounceNewStatefulStepMsg[K: (Hashable val & Equatable[K] val)] is
  AnnounceNewStatefulStepMsg val
```

#### Implements

* [AnnounceNewStatefulStepMsg](wallaroo-core-messages-AnnounceNewStatefulStepMsg) val

---

## Constructors

### create

```pony
new val create(
  id: U128 val,
  worker: String val,
  k: K,
  s_name: String val)
: KeyedAnnounceNewStatefulStepMsg[K] val^
```
#### Parameters

*   id: [U128](builtin-U128) val
*   worker: [String](builtin-String) val
*   k: K
*   s_name: [String](builtin-String) val

#### Returns

* [KeyedAnnounceNewStatefulStepMsg](wallaroo-core-messages-KeyedAnnounceNewStatefulStepMsg)\[K\] val^

---

## Public Functions

### update_registry

```pony
fun box update_registry(
  r: RouterRegistry tag)
: None val
```
#### Parameters

*   r: [RouterRegistry](wallaroo-ent-router_registry-RouterRegistry) tag

#### Returns

* [None](builtin-None) val

---

