# ClusterInitializer

```pony
actor tag ClusterInitializer
```

## Constructors

### create

```pony
new tag create(
  auth: AmbientAuth val,
  worker_name: String val,
  workers: USize val,
  connections: Connections tag,
  distributor: Distributor tag,
  layout_initializer: LayoutInitializer tag,
  data_addr: Array[String val] val,
  metrics_conn: MetricsSink tag,
  is_recovering: Bool val)
: ClusterInitializer tag^
```
#### Parameters

*   auth: [AmbientAuth](builtin-AmbientAuth) val
*   worker_name: [String](builtin-String) val
*   workers: [USize](builtin-USize) val
*   connections: [Connections](wallaroo-ent-network-Connections) tag
*   distributor: [Distributor](wallaroo-core-initialization-Distributor) tag
*   layout_initializer: [LayoutInitializer](wallaroo-core-initialization-LayoutInitializer) tag
*   data_addr: [Array](builtin-Array)\[[String](builtin-String) val\] val
*   metrics_conn: [MetricsSink](wallaroo-core-metrics-MetricsSink) tag
*   is_recovering: [Bool](builtin-Bool) val

#### Returns

* [ClusterInitializer](wallaroo-core-initialization-ClusterInitializer) tag^

---

## Public Behaviours

### start

```pony
be start(
  initializer_name: String val = seq)
```
#### Parameters

*   initializer_name: [String](builtin-String) val = seq

---

### identify_control_address

```pony
be identify_control_address(
  worker: String val,
  host: String val,
  service: String val)
```
#### Parameters

*   worker: [String](builtin-String) val
*   host: [String](builtin-String) val
*   service: [String](builtin-String) val

---

### identify_data_address

```pony
be identify_data_address(
  worker: String val,
  host: String val,
  service: String val)
```
#### Parameters

*   worker: [String](builtin-String) val
*   host: [String](builtin-String) val
*   service: [String](builtin-String) val

---

### distribute_local_topologies

```pony
be distribute_local_topologies(
  ts: HashMap[String val, LocalTopology val, HashEq[String val] val] val)
```
#### Parameters

*   ts: [HashMap](collections-HashMap)\[[String](builtin-String) val, [LocalTopology](wallaroo-core-initialization-LocalTopology) val, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val

---

### connections_ready

```pony
be connections_ready(
  worker_name: String val)
```
#### Parameters

*   worker_name: [String](builtin-String) val

---

### topology_ready

```pony
be topology_ready(
  worker_name: String val)
```
#### Parameters

*   worker_name: [String](builtin-String) val

---

## Private Functions

### _create_data_channel_listeners

```pony
fun box _create_data_channel_listeners()
: None val
```

#### Returns

* [None](builtin-None) val

---

### _create_interconnections

```pony
fun box _create_interconnections()
: None val
```

#### Returns

* [None](builtin-None) val

---

### _generate_addresses_map

```pony
fun box _generate_addresses_map()
: (HashMap[String val, (String val , String val), HashEq[String val] val] val , HashMap[String val, (String val , String val), HashEq[String val] val] val)
```

#### Returns

* ([HashMap](collections-HashMap)\[[String](builtin-String) val, ([String](builtin-String) val , [String](builtin-String) val), [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val , [HashMap](collections-HashMap)\[[String](builtin-String) val, ([String](builtin-String) val , [String](builtin-String) val), [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val)

---

