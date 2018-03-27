# ApplicationDistributor

```pony
actor tag ApplicationDistributor is
  Distributor tag
```

#### Implements

* [Distributor](wallaroo-core-initialization-Distributor) tag

---

## Constructors

### create

```pony
new tag create(
  auth: AmbientAuth val,
  application: Application val,
  local_topology_initializer: LocalTopologyInitializer tag)
: ApplicationDistributor tag^
```
#### Parameters

*   auth: [AmbientAuth](builtin-AmbientAuth) val
*   application: [Application](wallaroo-Application) val
*   local_topology_initializer: [LocalTopologyInitializer](wallaroo-core-initialization-LocalTopologyInitializer) tag

#### Returns

* [ApplicationDistributor](wallaroo-core-initialization-ApplicationDistributor) tag^

---

## Public Behaviours

### distribute

```pony
be distribute(
  cluster_initializer: (ClusterInitializer tag | None val),
  worker_count: USize val,
  worker_names: Array[String val] val,
  initializer_name: String val)
```
#### Parameters

*   cluster_initializer: ([ClusterInitializer](wallaroo-core-initialization-ClusterInitializer) tag | [None](builtin-None) val)
*   worker_count: [USize](builtin-USize) val
*   worker_names: [Array](builtin-Array)\[[String](builtin-String) val\] val
*   initializer_name: [String](builtin-String) val

---

### topology_ready

```pony
be topology_ready()
```

---

## Private Functions

### _distribute

```pony
fun ref _distribute(
  application: Application val,
  cluster_initializer: (ClusterInitializer tag | None val),
  worker_count: USize val,
  worker_names: Array[String val] val,
  initializer_name: String val)
: None val
```
#### Parameters

*   application: [Application](wallaroo-Application) val
*   cluster_initializer: ([ClusterInitializer](wallaroo-core-initialization-ClusterInitializer) tag | [None](builtin-None) val)
*   worker_count: [USize](builtin-USize) val
*   worker_names: [Array](builtin-Array)\[[String](builtin-String) val\] val
*   initializer_name: [String](builtin-String) val

#### Returns

* [None](builtin-None) val

---

### _add_edges_to_graph

```pony
fun ref _add_edges_to_graph(
  producer_ids: (U128 val | Array[U128 val] ref | None val),
  local_graphs: HashMap[String val, Dag[(StepBuilder val | SourceData val | EgressBuilder val | PreStatelessData val)] trn, HashEq[String val] val] trn,
  target_id: U128 val,
  worker: String val)
: HashMap[String val, Dag[(StepBuilder val | SourceData val | EgressBuilder val | PreStatelessData val)] trn, HashEq[String val] val] trn^ ?
```
#### Parameters

*   producer_ids: ([U128](builtin-U128) val | [Array](builtin-Array)\[[U128](builtin-U128) val\] ref | [None](builtin-None) val)
*   local_graphs: [HashMap](collections-HashMap)\[[String](builtin-String) val, [Dag](wallaroo_labs-dag-Dag)\[([StepBuilder](wallaroo-core-topology-StepBuilder) val | [SourceData](wallaroo-core-topology-SourceData) val | [EgressBuilder](wallaroo-core-topology-EgressBuilder) val | [PreStatelessData](wallaroo-core-topology-PreStatelessData) val)\] trn, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] trn
*   target_id: [U128](builtin-U128) val
*   worker: [String](builtin-String) val

#### Returns

* [HashMap](collections-HashMap)\[[String](builtin-String) val, [Dag](wallaroo_labs-dag-Dag)\[([StepBuilder](wallaroo-core-topology-StepBuilder) val | [SourceData](wallaroo-core-topology-SourceData) val | [EgressBuilder](wallaroo-core-topology-EgressBuilder) val | [PreStatelessData](wallaroo-core-topology-PreStatelessData) val)\] trn, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] trn^ ?

---

