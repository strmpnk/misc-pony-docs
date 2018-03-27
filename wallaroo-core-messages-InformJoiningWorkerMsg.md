# InformJoiningWorkerMsg

This message is sent as a response to a JoinCluster message. Currently it
only informs the new worker of metrics-related info


```pony
class val InformJoiningWorkerMsg is
  ChannelMsg val
```

#### Implements

* [ChannelMsg](wallaroo-core-messages-ChannelMsg) val

---

## Constructors

### create

```pony
new val create(
  sender: String val,
  app: String val,
  l_topology: LocalTopology val,
  m_host: String val,
  m_service: String val,
  c_addrs: HashMap[String val, (String val , String val), HashEq[String val] val] val,
  d_addrs: HashMap[String val, (String val , String val), HashEq[String val] val] val,
  w_names: Array[String val] val,
  p_blueprints: HashMap[String val, PartitionRouterBlueprint val, HashEq[String val] val] val,
  stateless_p_blueprints: HashMap[U128 val, StatelessPartitionRouterBlueprint val, HashEq[U128 val] val] val,
  omr_blueprint: OmniRouterBlueprint val)
: InformJoiningWorkerMsg val^
```
#### Parameters

*   sender: [String](builtin-String) val
*   app: [String](builtin-String) val
*   l_topology: [LocalTopology](wallaroo-core-initialization-LocalTopology) val
*   m_host: [String](builtin-String) val
*   m_service: [String](builtin-String) val
*   c_addrs: [HashMap](collections-HashMap)\[[String](builtin-String) val, ([String](builtin-String) val , [String](builtin-String) val), [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val
*   d_addrs: [HashMap](collections-HashMap)\[[String](builtin-String) val, ([String](builtin-String) val , [String](builtin-String) val), [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val
*   w_names: [Array](builtin-Array)\[[String](builtin-String) val\] val
*   p_blueprints: [HashMap](collections-HashMap)\[[String](builtin-String) val, [PartitionRouterBlueprint](wallaroo-core-topology-PartitionRouterBlueprint) val, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val
*   stateless_p_blueprints: [HashMap](collections-HashMap)\[[U128](builtin-U128) val, [StatelessPartitionRouterBlueprint](wallaroo-core-topology-StatelessPartitionRouterBlueprint) val, [HashEq](collections-HashEq)\[[U128](builtin-U128) val\] val\] val
*   omr_blueprint: [OmniRouterBlueprint](wallaroo-core-topology-OmniRouterBlueprint) val

#### Returns

* [InformJoiningWorkerMsg](wallaroo-core-messages-InformJoiningWorkerMsg) val^

---

## Public fields

* let sender_name: [String](builtin-String) val

---

* let local_topology: [LocalTopology](wallaroo-core-initialization-LocalTopology) val

---

* let metrics_app_name: [String](builtin-String) val

---

* let metrics_host: [String](builtin-String) val

---

* let metrics_service: [String](builtin-String) val

---

* let control_addrs: [HashMap](collections-HashMap)\[[String](builtin-String) val, ([String](builtin-String) val , [String](builtin-String) val), [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val

---

* let data_addrs: [HashMap](collections-HashMap)\[[String](builtin-String) val, ([String](builtin-String) val , [String](builtin-String) val), [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val

---

* let worker_names: [Array](builtin-Array)\[[String](builtin-String) val\] val

---

* let partition_router_blueprints: [HashMap](collections-HashMap)\[[String](builtin-String) val, [PartitionRouterBlueprint](wallaroo-core-topology-PartitionRouterBlueprint) val, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val

---

* let stateless_partition_router_blueprints: [HashMap](collections-HashMap)\[[U128](builtin-U128) val, [StatelessPartitionRouterBlueprint](wallaroo-core-topology-StatelessPartitionRouterBlueprint) val, [HashEq](collections-HashEq)\[[U128](builtin-U128) val\] val\] val

---

* let omni_router_blueprint: [OmniRouterBlueprint](wallaroo-core-topology-OmniRouterBlueprint) val

---

