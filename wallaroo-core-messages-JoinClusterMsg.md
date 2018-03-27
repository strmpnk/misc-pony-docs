# JoinClusterMsg

This message is sent from a worker requesting to join a running cluster to
any existing worker in the cluster.


```pony
class val JoinClusterMsg is
  ChannelMsg val
```

#### Implements

* [ChannelMsg](wallaroo-core-messages-ChannelMsg) val

---

## Constructors

### create

```pony
new val create(
  w: String val,
  wc: USize val)
: JoinClusterMsg val^
```
#### Parameters

*   w: [String](builtin-String) val
*   wc: [USize](builtin-USize) val

#### Returns

* [JoinClusterMsg](wallaroo-core-messages-JoinClusterMsg) val^

---

## Public fields

* let worker_name: [String](builtin-String) val

---

* let worker_count: [USize](builtin-USize) val

---

