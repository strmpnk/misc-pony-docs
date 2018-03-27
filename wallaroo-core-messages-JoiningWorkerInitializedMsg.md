# JoiningWorkerInitializedMsg

```pony
class val JoiningWorkerInitializedMsg is
  ChannelMsg val
```

#### Implements

* [ChannelMsg](wallaroo-core-messages-ChannelMsg) val

---

## Constructors

### create

```pony
new val create(
  name: String val,
  c_addr: (String val , String val),
  d_addr: (String val , String val))
: JoiningWorkerInitializedMsg val^
```
#### Parameters

*   name: [String](builtin-String) val
*   c_addr: ([String](builtin-String) val , [String](builtin-String) val)
*   d_addr: ([String](builtin-String) val , [String](builtin-String) val)

#### Returns

* [JoiningWorkerInitializedMsg](wallaroo-core-messages-JoiningWorkerInitializedMsg) val^

---

## Public fields

* let worker_name: [String](builtin-String) val

---

* let control_addr: ([String](builtin-String) val , [String](builtin-String) val)

---

* let data_addr: ([String](builtin-String) val , [String](builtin-String) val)

---

