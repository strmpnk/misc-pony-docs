# Connections

```pony
actor tag Connections is
  Cluster tag
```

#### Implements

* [Cluster](wallaroo-ent-network-Cluster) tag

---

## Constructors

### create

```pony
new tag create(
  app_name: String val,
  worker_name: String val,
  auth: AmbientAuth val,
  c_host: String val,
  c_service: String val,
  d_host: String val,
  d_service: String val,
  metrics_conn: MetricsSink tag,
  metrics_host: String val,
  metrics_service: String val,
  is_initializer: Bool val,
  connection_addresses_file: String val,
  is_joining: Bool val,
  spike_config: (SpikeConfig val | None val) = seq,
  event_log: EventLog tag,
  log_rotation: Bool val = seq,
  recovery_file_cleaner: (RecoveryFileCleaner tag | None val) = seq)
: Connections tag^
```
#### Parameters

*   app_name: [String](builtin-String) val
*   worker_name: [String](builtin-String) val
*   auth: [AmbientAuth](builtin-AmbientAuth) val
*   c_host: [String](builtin-String) val
*   c_service: [String](builtin-String) val
*   d_host: [String](builtin-String) val
*   d_service: [String](builtin-String) val
*   metrics_conn: [MetricsSink](wallaroo-core-metrics-MetricsSink) tag
*   metrics_host: [String](builtin-String) val
*   metrics_service: [String](builtin-String) val
*   is_initializer: [Bool](builtin-Bool) val
*   connection_addresses_file: [String](builtin-String) val
*   is_joining: [Bool](builtin-Bool) val
*   spike_config: ([SpikeConfig](wallaroo-ent-spike-SpikeConfig) val | [None](builtin-None) val) = seq
*   event_log: [EventLog](wallaroo-ent-recovery-EventLog) tag
*   log_rotation: [Bool](builtin-Bool) val = seq
*   recovery_file_cleaner: ([RecoveryFileCleaner](wallaroo-core-common-RecoveryFileCleaner) tag | [None](builtin-None) val) = seq

#### Returns

* [Connections](wallaroo-ent-network-Connections) tag^

---

## Public Behaviours

### register_my_control_addr

```pony
be register_my_control_addr(
  host: String val,
  service: String val)
```
#### Parameters

*   host: [String](builtin-String) val
*   service: [String](builtin-String) val

---

### register_my_data_addr

```pony
be register_my_data_addr(
  host: String val,
  service: String val)
```
#### Parameters

*   host: [String](builtin-String) val
*   service: [String](builtin-String) val

---

### register_disposable

```pony
be register_disposable(
  d: DisposableActor tag)
```
#### Parameters

*   d: [DisposableActor](builtin-DisposableActor) tag

---

### make_and_register_recoverable_listener

```pony
be make_and_register_recoverable_listener(
  auth: (AmbientAuth val | NetAuth val | TCPAuth val | 
    TCPListenAuth val),
  notifier: TCPListenNotify iso,
  recovery_addr_file: FilePath val,
  host: String val = seq,
  port: String val = seq)
```
#### Parameters

*   auth: ([AmbientAuth](builtin-AmbientAuth) val | [NetAuth](net-NetAuth) val | [TCPAuth](net-TCPAuth) val | 
    [TCPListenAuth](net-TCPListenAuth) val)
*   notifier: [TCPListenNotify](net-TCPListenNotify) iso
*   recovery_addr_file: [FilePath](files-FilePath) val
*   host: [String](builtin-String) val = seq
*   port: [String](builtin-String) val = seq

---

### make_and_register_recoverable_data_channel_listener

```pony
be make_and_register_recoverable_data_channel_listener(
  auth: (AmbientAuth val | NetAuth val | TCPAuth val | 
    TCPListenAuth val),
  notifier: DataChannelListenNotify iso,
  router_registry: RouterRegistry tag,
  recovery_addr_file: FilePath val,
  host: String val = seq,
  port: String val = seq)
```
#### Parameters

*   auth: ([AmbientAuth](builtin-AmbientAuth) val | [NetAuth](net-NetAuth) val | [TCPAuth](net-TCPAuth) val | 
    [TCPListenAuth](net-TCPListenAuth) val)
*   notifier: [DataChannelListenNotify](wallaroo-core-data_channel-DataChannelListenNotify) iso
*   router_registry: [RouterRegistry](wallaroo-ent-router_registry-RouterRegistry) tag
*   recovery_addr_file: [FilePath](files-FilePath) val
*   host: [String](builtin-String) val = seq
*   port: [String](builtin-String) val = seq

---

### create_initializer_data_channel_listener

```pony
be create_initializer_data_channel_listener(
  data_receivers: DataReceivers tag,
  recovery_replayer: RecoveryReplayer tag,
  router_registry: RouterRegistry tag,
  cluster_initializer: ClusterInitializer tag,
  data_channel_file: FilePath val,
  layout_initializer: LayoutInitializer tag)
```
#### Parameters

*   data_receivers: [DataReceivers](wallaroo-ent-data_receiver-DataReceivers) tag
*   recovery_replayer: [RecoveryReplayer](wallaroo-ent-recovery-RecoveryReplayer) tag
*   router_registry: [RouterRegistry](wallaroo-ent-router_registry-RouterRegistry) tag
*   cluster_initializer: [ClusterInitializer](wallaroo-core-initialization-ClusterInitializer) tag
*   data_channel_file: [FilePath](files-FilePath) val
*   layout_initializer: [LayoutInitializer](wallaroo-core-initialization-LayoutInitializer) tag

---

### send_control

```pony
be send_control(
  worker: String val,
  data: Array[(String val | Array[U8 val] val)] val)
```
#### Parameters

*   worker: [String](builtin-String) val
*   data: [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val

---

### send_control_to_cluster

```pony
be send_control_to_cluster(
  data: Array[(String val | Array[U8 val] val)] val)
```
#### Parameters

*   data: [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val

---

### send_control_to_random

```pony
be send_control_to_random(
  data: Array[(String val | Array[U8 val] val)] val)
```
#### Parameters

*   data: [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val

---

### send_data

```pony
be send_data(
  worker: String val,
  data: Array[(String val | Array[U8 val] val)] val)
```
#### Parameters

*   worker: [String](builtin-String) val
*   data: [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val

---

### send_data_to_cluster

```pony
be send_data_to_cluster(
  data: Array[(String val | Array[U8 val] val)] val)
```
#### Parameters

*   data: [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val

---

### disconnect_from

```pony
be disconnect_from(
  worker: String val)
```
#### Parameters

*   worker: [String](builtin-String) val

---

### notify_cluster_of_new_stateful_step\[K: ([Hashable](collections-Hashable) val & [Equatable](builtin-Equatable)\[K\] val)\]

```pony
be notify_cluster_of_new_stateful_step[K: (Hashable val & Equatable[K] val)](
  id: U128 val,
  key: K,
  state_name: String val,
  exclusions: Array[String val] val = seq)
```
#### Parameters

*   id: [U128](builtin-U128) val
*   key: K
*   state_name: [String](builtin-String) val
*   exclusions: [Array](builtin-Array)\[[String](builtin-String) val\] val = seq

---

### stop_the_world

```pony
be stop_the_world(
  exclusions: Array[String val] val = seq)
```
#### Parameters

*   exclusions: [Array](builtin-Array)\[[String](builtin-String) val\] val = seq

---

### request_cluster_unmute

```pony
be request_cluster_unmute()
```

---

### create_boundary_to_joining_worker

```pony
be create_boundary_to_joining_worker(
  target: String val,
  boundary_id: U128 val,
  local_topology_initializer: LocalTopologyInitializer tag)
```
#### Parameters

*   target: [String](builtin-String) val
*   boundary_id: [U128](builtin-U128) val
*   local_topology_initializer: [LocalTopologyInitializer](wallaroo-core-initialization-LocalTopologyInitializer) tag

---

### update_boundaries

```pony
be update_boundaries(
  layout_initializer: LayoutInitializer tag,
  recovering: Bool val = seq)
```
#### Parameters

*   layout_initializer: [LayoutInitializer](wallaroo-core-initialization-LayoutInitializer) tag
*   recovering: [Bool](builtin-Bool) val = seq

---

### create_connections

```pony
be create_connections(
  control_addrs: HashMap[String val, (String val , String val), HashEq[String val] val] val,
  data_addrs: HashMap[String val, (String val , String val), HashEq[String val] val] val,
  layout_initializer: LayoutInitializer tag,
  router_registry: (RouterRegistry tag | None val) = seq)
```
#### Parameters

*   control_addrs: [HashMap](collections-HashMap)\[[String](builtin-String) val, ([String](builtin-String) val , [String](builtin-String) val), [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val
*   data_addrs: [HashMap](collections-HashMap)\[[String](builtin-String) val, ([String](builtin-String) val , [String](builtin-String) val), [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val
*   layout_initializer: [LayoutInitializer](wallaroo-core-initialization-LayoutInitializer) tag
*   router_registry: ([RouterRegistry](wallaroo-ent-router_registry-RouterRegistry) tag | [None](builtin-None) val) = seq

---

### save_connections

```pony
be save_connections()
```

---

### quick_initialize_data_connections

```pony
be quick_initialize_data_connections(
  li: LayoutInitializer tag)
```
#### Parameters

*   li: [LayoutInitializer](wallaroo-core-initialization-LayoutInitializer) tag

---

### create_routers_from_blueprints

```pony
be create_routers_from_blueprints(
  pr_blueprints: HashMap[String val, PartitionRouterBlueprint val, HashEq[String val] val] val,
  spr_blueprints: HashMap[U128 val, StatelessPartitionRouterBlueprint val, HashEq[U128 val] val] val,
  omr_blueprint: OmniRouterBlueprint val,
  local_sinks: HashMap[U128 val, Consumer tag, HashEq[U128 val] val] val,
  router_registry: RouterRegistry tag,
  lti: LocalTopologyInitializer tag)
```
#### Parameters

*   pr_blueprints: [HashMap](collections-HashMap)\[[String](builtin-String) val, [PartitionRouterBlueprint](wallaroo-core-topology-PartitionRouterBlueprint) val, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val
*   spr_blueprints: [HashMap](collections-HashMap)\[[U128](builtin-U128) val, [StatelessPartitionRouterBlueprint](wallaroo-core-topology-StatelessPartitionRouterBlueprint) val, [HashEq](collections-HashEq)\[[U128](builtin-U128) val\] val\] val
*   omr_blueprint: [OmniRouterBlueprint](wallaroo-core-topology-OmniRouterBlueprint) val
*   local_sinks: [HashMap](collections-HashMap)\[[U128](builtin-U128) val, [Consumer](wallaroo-core-common-Consumer) tag, [HashEq](collections-HashEq)\[[U128](builtin-U128) val\] val\] val
*   router_registry: [RouterRegistry](wallaroo-ent-router_registry-RouterRegistry) tag
*   lti: [LocalTopologyInitializer](wallaroo-core-initialization-LocalTopologyInitializer) tag

---

### recover_connections

```pony
be recover_connections(
  layout_initializer: LayoutInitializer tag)
```
#### Parameters

*   layout_initializer: [LayoutInitializer](wallaroo-core-initialization-LayoutInitializer) tag

---

### create_control_connection

```pony
be create_control_connection(
  target_name: String val,
  host: String val,
  service: String val)
```
#### Parameters

*   target_name: [String](builtin-String) val
*   host: [String](builtin-String) val
*   service: [String](builtin-String) val

---

### reconnect_data_connection

```pony
be reconnect_data_connection(
  target_name: String val)
```
#### Parameters

*   target_name: [String](builtin-String) val

---

### create_data_connection

```pony
be create_data_connection(
  target_name: String val,
  host: String val,
  service: String val)
```
#### Parameters

*   target_name: [String](builtin-String) val
*   host: [String](builtin-String) val
*   service: [String](builtin-String) val

---

### create_data_connection_to_joining_worker

```pony
be create_data_connection_to_joining_worker(
  target_name: String val,
  host: String val,
  service: String val,
  li: LayoutInitializer tag)
```
#### Parameters

*   target_name: [String](builtin-String) val
*   host: [String](builtin-String) val
*   service: [String](builtin-String) val
*   li: [LayoutInitializer](wallaroo-core-initialization-LayoutInitializer) tag

---

### update_boundary_ids

```pony
be update_boundary_ids(
  boundary_ids: HashMap[String val, U128 val, HashEq[String val] val] val)
```
#### Parameters

*   boundary_ids: [HashMap](collections-HashMap)\[[String](builtin-String) val, [U128](builtin-U128) val, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val

---

### inform_joining_worker

```pony
be inform_joining_worker(
  conn: TCPConnection tag,
  worker: String val,
  local_topology: LocalTopology val,
  partition_blueprints: HashMap[String val, PartitionRouterBlueprint val, HashEq[String val] val] val,
  stateless_partition_blueprints: HashMap[U128 val, StatelessPartitionRouterBlueprint val, HashEq[U128 val] val] val,
  omr_blueprint: OmniRouterBlueprint val)
```
#### Parameters

*   conn: [TCPConnection](net-TCPConnection) tag
*   worker: [String](builtin-String) val
*   local_topology: [LocalTopology](wallaroo-core-initialization-LocalTopology) val
*   partition_blueprints: [HashMap](collections-HashMap)\[[String](builtin-String) val, [PartitionRouterBlueprint](wallaroo-core-topology-PartitionRouterBlueprint) val, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val
*   stateless_partition_blueprints: [HashMap](collections-HashMap)\[[U128](builtin-U128) val, [StatelessPartitionRouterBlueprint](wallaroo-core-topology-StatelessPartitionRouterBlueprint) val, [HashEq](collections-HashEq)\[[U128](builtin-U128) val\] val\] val
*   omr_blueprint: [OmniRouterBlueprint](wallaroo-core-topology-OmniRouterBlueprint) val

---

### inform_cluster_of_join

```pony
be inform_cluster_of_join()
```

---

### inform_worker_of_boundary_count

```pony
be inform_worker_of_boundary_count(
  target_worker: String val,
  count: USize val)
```
#### Parameters

*   target_worker: [String](builtin-String) val
*   count: [USize](builtin-USize) val

---

### ack_migration_batch_complete

Called when this worker has just joined and it needs to ack to sender_name
that immigration of a batch is complete


```pony
be ack_migration_batch_complete(
  ack_target: String val)
```
#### Parameters

*   ack_target: [String](builtin-String) val

---

### dispose

```pony
be dispose()
```

---

### shutdown

```pony
be shutdown()
```

---

### rotate_log_files

Instruct a worker to rotate its log files.
If worker_name isn't given, do nothing.


```pony
be rotate_log_files(
  worker_name: String val)
```
#### Parameters

*   worker_name: [String](builtin-String) val

---

## Private Functions

### _register_disposable

```pony
fun ref _register_disposable(
  d: DisposableActor tag)
: None val
```
#### Parameters

*   d: [DisposableActor](builtin-DisposableActor) tag

#### Returns

* [None](builtin-None) val

---

### _send_control

```pony
fun box _send_control(
  worker: String val,
  data: Array[(String val | Array[U8 val] val)] val)
: None val
```
#### Parameters

*   worker: [String](builtin-String) val
*   data: [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val

#### Returns

* [None](builtin-None) val

---

### _send_control_to_cluster

```pony
fun box _send_control_to_cluster(
  data: Array[(String val | Array[U8 val] val)] val)
: None val
```
#### Parameters

*   data: [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val

#### Returns

* [None](builtin-None) val

---

### _send_control_to_random

```pony
fun box _send_control_to_random(
  data: Array[(String val | Array[U8 val] val)] val)
: None val
```
#### Parameters

*   data: [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val

#### Returns

* [None](builtin-None) val

---

### _send_data

```pony
fun box _send_data(
  worker: String val,
  data: Array[(String val | Array[U8 val] val)] val)
: None val
```
#### Parameters

*   worker: [String](builtin-String) val
*   data: [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val

#### Returns

* [None](builtin-None) val

---

### _update_boundaries

```pony
fun box _update_boundaries(
  layout_initializer: LayoutInitializer tag,
  recovering: Bool val = seq,
  router_registry: (RouterRegistry tag | None val) = seq)
: None val
```
#### Parameters

*   layout_initializer: [LayoutInitializer](wallaroo-core-initialization-LayoutInitializer) tag
*   recovering: [Bool](builtin-Bool) val = seq
*   router_registry: ([RouterRegistry](wallaroo-ent-router_registry-RouterRegistry) tag | [None](builtin-None) val) = seq

#### Returns

* [None](builtin-None) val

---

### _save_connections

```pony
fun box _save_connections(
  control_addrs: HashMap[String val, (String val , String val), HashEq[String val] val] box,
  data_addrs: HashMap[String val, (String val , String val), HashEq[String val] val] box)
: None val
```
#### Parameters

*   control_addrs: [HashMap](collections-HashMap)\[[String](builtin-String) val, ([String](builtin-String) val , [String](builtin-String) val), [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] box
*   data_addrs: [HashMap](collections-HashMap)\[[String](builtin-String) val, ([String](builtin-String) val , [String](builtin-String) val), [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] box

#### Returns

* [None](builtin-None) val

---

### _create_control_connection

```pony
fun ref _create_control_connection(
  target_name: String val,
  host: String val,
  service: String val)
: None val
```
#### Parameters

*   target_name: [String](builtin-String) val
*   host: [String](builtin-String) val
*   service: [String](builtin-String) val

#### Returns

* [None](builtin-None) val

---

### _create_data_connection

```pony
fun ref _create_data_connection(
  target_name: String val,
  host: String val,
  service: String val)
: None val
```
#### Parameters

*   target_name: [String](builtin-String) val
*   host: [String](builtin-String) val
*   service: [String](builtin-String) val

#### Returns

* [None](builtin-None) val

---

### _has_registered_my_addrs

```pony
fun box _has_registered_my_addrs()
: Bool val
```

#### Returns

* [Bool](builtin-Bool) val

---

### _shutdown

```pony
fun ref _shutdown()
: None val
```

#### Returns

* [None](builtin-None) val

---

### _rotate_log_files

```pony
fun box _rotate_log_files(
  worker_name: String val)
: None val
```
#### Parameters

*   worker_name: [String](builtin-String) val

#### Returns

* [None](builtin-None) val

---

