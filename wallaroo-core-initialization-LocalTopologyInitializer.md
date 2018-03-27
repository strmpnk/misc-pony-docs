# LocalTopologyInitializer

```pony
actor tag LocalTopologyInitializer is
  LayoutInitializer tag
```

#### Implements

* [LayoutInitializer](wallaroo-core-initialization-LayoutInitializer) tag

---

## Constructors

### create

```pony
new tag create(
  app: Application val,
  worker_name: String val,
  env: Env val,
  auth: AmbientAuth val,
  connections: Connections tag,
  router_registry: RouterRegistry tag,
  metrics_conn: MetricsSink tag,
  is_initializer: Bool val,
  data_receivers: DataReceivers tag,
  event_log: EventLog tag,
  recovery: Recovery tag,
  recovery_replayer: RecoveryReplayer tag,
  local_topology_file: String val,
  data_channel_file: String val,
  worker_names_file: String val,
  cluster_manager: (ClusterManager tag | None val) = seq,
  is_joining: Bool val = seq)
: LocalTopologyInitializer tag^
```
#### Parameters

*   app: [Application](wallaroo-Application) val
*   worker_name: [String](builtin-String) val
*   env: [Env](builtin-Env) val
*   auth: [AmbientAuth](builtin-AmbientAuth) val
*   connections: [Connections](wallaroo-ent-network-Connections) tag
*   router_registry: [RouterRegistry](wallaroo-ent-router_registry-RouterRegistry) tag
*   metrics_conn: [MetricsSink](wallaroo-core-metrics-MetricsSink) tag
*   is_initializer: [Bool](builtin-Bool) val
*   data_receivers: [DataReceivers](wallaroo-ent-data_receiver-DataReceivers) tag
*   event_log: [EventLog](wallaroo-ent-recovery-EventLog) tag
*   recovery: [Recovery](wallaroo-ent-recovery-Recovery) tag
*   recovery_replayer: [RecoveryReplayer](wallaroo-ent-recovery-RecoveryReplayer) tag
*   local_topology_file: [String](builtin-String) val
*   data_channel_file: [String](builtin-String) val
*   worker_names_file: [String](builtin-String) val
*   cluster_manager: ([ClusterManager](wallaroo-ent-cluster_manager-ClusterManager) tag | [None](builtin-None) val) = seq
*   is_joining: [Bool](builtin-Bool) val = seq

#### Returns

* [LocalTopologyInitializer](wallaroo-core-initialization-LocalTopologyInitializer) tag^

---

## Public fields

* let sl_builders: [Array](builtin-Array)\[[SourceListenerBuilder](wallaroo-core-source-SourceListenerBuilder) val\] ref

---

## Public Behaviours

### update_topology

```pony
be update_topology(
  t: LocalTopology val)
```
#### Parameters

*   t: [LocalTopology](wallaroo-core-initialization-LocalTopology) val

---

### add_joining_worker

```pony
be add_joining_worker(
  w: String val,
  joining_host: String val,
  control_addr: (String val , String val),
  data_addr: (String val , String val))
```
#### Parameters

*   w: [String](builtin-String) val
*   joining_host: [String](builtin-String) val
*   control_addr: ([String](builtin-String) val , [String](builtin-String) val)
*   data_addr: ([String](builtin-String) val , [String](builtin-String) val)

---

### initiate_shrink

```pony
be initiate_shrink(
  target_workers: Array[String val] val,
  shrink_count: U64 val,
  conn: TCPConnection tag)
```
#### Parameters

*   target_workers: [Array](builtin-Array)\[[String](builtin-String) val\] val
*   shrink_count: [U64](builtin-U64) val
*   conn: [TCPConnection](net-TCPConnection) tag

---

### take_over_initiate_shrink

```pony
be take_over_initiate_shrink(
  remaining_workers: Array[String val] val,
  leaving_workers: Array[String val] val)
```
#### Parameters

*   remaining_workers: [Array](builtin-Array)\[[String](builtin-String) val\] val
*   leaving_workers: [Array](builtin-Array)\[[String](builtin-String) val\] val

---

### prepare_shrink

```pony
be prepare_shrink(
  remaining_workers: Array[String val] val,
  leaving_workers: Array[String val] val)
```
#### Parameters

*   remaining_workers: [Array](builtin-Array)\[[String](builtin-String) val\] val
*   leaving_workers: [Array](builtin-Array)\[[String](builtin-String) val\] val

---

### add_boundary_to_joining_worker

```pony
be add_boundary_to_joining_worker(
  w: String val,
  boundary: OutgoingBoundary tag,
  builder: OutgoingBoundaryBuilder val)
```
#### Parameters

*   w: [String](builtin-String) val
*   boundary: [OutgoingBoundary](wallaroo-core-boundary-OutgoingBoundary) tag
*   builder: [OutgoingBoundaryBuilder](wallaroo-core-boundary-OutgoingBoundaryBuilder) val

---

### update_boundaries

```pony
be update_boundaries(
  bs: HashMap[String val, OutgoingBoundary tag, HashEq[String val] val] val,
  bbs: HashMap[String val, OutgoingBoundaryBuilder val, HashEq[String val] val] val)
```
#### Parameters

*   bs: [HashMap](collections-HashMap)\[[String](builtin-String) val, [OutgoingBoundary](wallaroo-core-boundary-OutgoingBoundary) tag, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val
*   bbs: [HashMap](collections-HashMap)\[[String](builtin-String) val, [OutgoingBoundaryBuilder](wallaroo-core-boundary-OutgoingBoundaryBuilder) val, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val

---

### create_data_channel_listener

```pony
be create_data_channel_listener(
  ws: Array[String val] val,
  host: String val,
  service: String val,
  cluster_initializer: (ClusterInitializer tag | None val) = seq)
```
#### Parameters

*   ws: [Array](builtin-Array)\[[String](builtin-String) val\] val
*   host: [String](builtin-String) val
*   service: [String](builtin-String) val
*   cluster_initializer: ([ClusterInitializer](wallaroo-core-initialization-ClusterInitializer) tag | [None](builtin-None) val) = seq

---

### create_connections

```pony
be create_connections(
  control_addrs: HashMap[String val, (String val , String val), HashEq[String val] val] val,
  data_addrs: HashMap[String val, (String val , String val), HashEq[String val] val] val)
```
#### Parameters

*   control_addrs: [HashMap](collections-HashMap)\[[String](builtin-String) val, ([String](builtin-String) val , [String](builtin-String) val), [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val
*   data_addrs: [HashMap](collections-HashMap)\[[String](builtin-String) val, ([String](builtin-String) val , [String](builtin-String) val), [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val

---

### quick_initialize_data_connections

Called as part of joining worker's initialization


```pony
be quick_initialize_data_connections()
```

---

### set_omni_router

```pony
be set_omni_router(
  omr: OmniRouter val)
```
#### Parameters

*   omr: [OmniRouter](wallaroo-core-topology-OmniRouter) val

---

### set_partition_router_blueprints

```pony
be set_partition_router_blueprints(
  pr_blueprints: HashMap[String val, PartitionRouterBlueprint val, HashEq[String val] val] val,
  spr_blueprints: HashMap[U128 val, StatelessPartitionRouterBlueprint val, HashEq[U128 val] val] val,
  omr_blueprint: OmniRouterBlueprint val)
```
#### Parameters

*   pr_blueprints: [HashMap](collections-HashMap)\[[String](builtin-String) val, [PartitionRouterBlueprint](wallaroo-core-topology-PartitionRouterBlueprint) val, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val
*   spr_blueprints: [HashMap](collections-HashMap)\[[U128](builtin-U128) val, [StatelessPartitionRouterBlueprint](wallaroo-core-topology-StatelessPartitionRouterBlueprint) val, [HashEq](collections-HashEq)\[[U128](builtin-U128) val\] val\] val
*   omr_blueprint: [OmniRouterBlueprint](wallaroo-core-topology-OmniRouterBlueprint) val

---

### recover_and_initialize

```pony
be recover_and_initialize(
  ws: Array[String val] val,
  cluster_initializer: (ClusterInitializer tag | None val) = seq)
```
#### Parameters

*   ws: [Array](builtin-Array)\[[String](builtin-String) val\] val
*   cluster_initializer: ([ClusterInitializer](wallaroo-core-initialization-ClusterInitializer) tag | [None](builtin-None) val) = seq

---

### initialize

```pony
be initialize(
  cluster_initializer: (ClusterInitializer tag | None val) = seq,
  recovering: Bool val = seq)
```
#### Parameters

*   cluster_initializer: ([ClusterInitializer](wallaroo-core-initialization-ClusterInitializer) tag | [None](builtin-None) val) = seq
*   recovering: [Bool](builtin-Bool) val = seq

---

### update_state_step_entry\[Key: ([Hashable](collections-Hashable) val & [Equatable](builtin-Equatable)\[Key\] val)\]

```pony
be update_state_step_entry[Key: (Hashable val & Equatable[Key] val)](
  state_name: String val,
  key: Key,
  pa: ProxyAddress val)
```
#### Parameters

*   state_name: [String](builtin-String) val
*   key: Key
*   pa: [ProxyAddress](wallaroo-core-topology-ProxyAddress) val

---

### receive_immigrant_step

```pony
be receive_immigrant_step(
  msg: StepMigrationMsg val)
```
#### Parameters

*   msg: [StepMigrationMsg](wallaroo-core-messages-StepMigrationMsg) val

---

### shrinkable_query

```pony
be shrinkable_query(
  conn: TCPConnection tag)
```
#### Parameters

*   conn: [TCPConnection](net-TCPConnection) tag

---

### partition_query

```pony
be partition_query(
  conn: TCPConnection tag)
```
#### Parameters

*   conn: [TCPConnection](net-TCPConnection) tag

---

### partition_count_query

```pony
be partition_count_query(
  conn: TCPConnection tag)
```
#### Parameters

*   conn: [TCPConnection](net-TCPConnection) tag

---

### cluster_status_query

```pony
be cluster_status_query(
  conn: TCPConnection tag)
```
#### Parameters

*   conn: [TCPConnection](net-TCPConnection) tag

---

### initialize_join_initializables

```pony
be initialize_join_initializables()
```

---

### report_created

```pony
be report_created(
  initializable: Initializable tag)
```
#### Parameters

*   initializable: [Initializable](wallaroo-core-common-Initializable) tag

---

### report_initialized

```pony
be report_initialized(
  initializable: Initializable tag)
```
#### Parameters

*   initializable: [Initializable](wallaroo-core-common-Initializable) tag

---

### report_ready_to_work

```pony
be report_ready_to_work(
  initializable: Initializable tag)
```
#### Parameters

*   initializable: [Initializable](wallaroo-core-common-Initializable) tag

---

### report_event_log_ready_to_work

```pony
be report_event_log_ready_to_work()
```

---

### inform_joining_worker

```pony
be inform_joining_worker(
  conn: TCPConnection tag,
  worker_name: String val,
  worker_count: USize val)
```
#### Parameters

*   conn: [TCPConnection](net-TCPConnection) tag
*   worker_name: [String](builtin-String) val
*   worker_count: [USize](builtin-USize) val

---

### request_new_worker

```pony
be request_new_worker()
```

---

## Private Functions

### _are_valid_shrink_candidates

```pony
fun box _are_valid_shrink_candidates(
  candidates: Array[String val] val)
: Bool val
```
#### Parameters

*   candidates: [Array](builtin-Array)\[[String](builtin-String) val\] val

#### Returns

* [Bool](builtin-Bool) val

---

### _get_shrink_candidates

```pony
fun box _get_shrink_candidates(
  count: USize val)
: Array[String val] val
```
#### Parameters

*   count: [USize](builtin-USize) val

#### Returns

* [Array](builtin-Array)\[[String](builtin-String) val\] val

---

### _add_worker_name

```pony
fun ref _add_worker_name(
  w: String val)
: None val
```
#### Parameters

*   w: [String](builtin-String) val

#### Returns

* [None](builtin-None) val

---

### _remove_worker_names

```pony
fun ref _remove_worker_names(
  ws: Array[String val] val)
: Array[String val] val
```
#### Parameters

*   ws: [Array](builtin-Array)\[[String](builtin-String) val\] val

#### Returns

* [Array](builtin-Array)\[[String](builtin-String) val\] val

---

### _add_boundary

```pony
fun ref _add_boundary(
  target_worker: String val,
  boundary: OutgoingBoundary tag,
  builder: OutgoingBoundaryBuilder val)
: None val
```
#### Parameters

*   target_worker: [String](builtin-String) val
*   boundary: [OutgoingBoundary](wallaroo-core-boundary-OutgoingBoundary) tag
*   builder: [OutgoingBoundaryBuilder](wallaroo-core-boundary-OutgoingBoundaryBuilder) val

#### Returns

* [None](builtin-None) val

---

### _save_worker_names

Save the list of worker names to a file.


```pony
fun ref _save_worker_names()
: None val
```

#### Returns

* [None](builtin-None) val

---

### _save_local_topology

```pony
fun ref _save_local_topology()
: None val
```

#### Returns

* [None](builtin-None) val

---

### _initialize_joining_worker

```pony
fun ref _initialize_joining_worker()
: None val
```

#### Returns

* [None](builtin-None) val

---

### _initialize_join_initializables

```pony
fun ref _initialize_join_initializables()
: None val
```

#### Returns

* [None](builtin-None) val

---

### _complete_initialization_lifecycle

```pony
fun ref _complete_initialization_lifecycle()
: None val
```

#### Returns

* [None](builtin-None) val

---

### _application_ready_to_work

```pony
fun ref _application_ready_to_work()
: None val
```

#### Returns

* [None](builtin-None) val

---

### _spin_up_source_listeners

```pony
fun ref _spin_up_source_listeners()
: None val
```

#### Returns

* [None](builtin-None) val

---

### _is_ready_for_building

```pony
fun box _is_ready_for_building(
  node: DagNode[(StepBuilder val | SourceData val | EgressBuilder val | PreStatelessData val)] val,
  built_routers: HashMap[U128 val, Router val, HashEq[U128 val] val] ref)
: Bool val
```
#### Parameters

*   node: [DagNode](wallaroo_labs-dag-DagNode)\[([StepBuilder](wallaroo-core-topology-StepBuilder) val | [SourceData](wallaroo-core-topology-SourceData) val | [EgressBuilder](wallaroo-core-topology-EgressBuilder) val | [PreStatelessData](wallaroo-core-topology-PreStatelessData) val)\] val
*   built_routers: [HashMap](collections-HashMap)\[[U128](builtin-U128) val, [Router](wallaroo-core-topology-Router) val, [HashEq](collections-HashEq)\[[U128](builtin-U128) val\] val\] ref

#### Returns

* [Bool](builtin-Bool) val

---

### _get_output_node_ids

```pony
fun box _get_output_node_ids(
  node: DagNode[(StepBuilder val | SourceData val | EgressBuilder val | PreStatelessData val)] val)
: Array[U128 val] val ?
```
#### Parameters

*   node: [DagNode](wallaroo_labs-dag-DagNode)\[([StepBuilder](wallaroo-core-topology-StepBuilder) val | [SourceData](wallaroo-core-topology-SourceData) val | [EgressBuilder](wallaroo-core-topology-EgressBuilder) val | [PreStatelessData](wallaroo-core-topology-PreStatelessData) val)\] val

#### Returns

* [Array](builtin-Array)\[[U128](builtin-U128) val\] val ?

---

