# RouterRegistry

```pony
actor tag RouterRegistry
```

## Constructors

### create

```pony
new tag create(
  auth: AmbientAuth val,
  worker_name: String val,
  data_receivers: DataReceivers tag,
  c: Connections tag,
  recovery_file_cleaner: RecoveryFileCleaner tag,
  stop_the_world_pause: U64 val)
: RouterRegistry tag^
```
#### Parameters

*   auth: [AmbientAuth](builtin-AmbientAuth) val
*   worker_name: [String](builtin-String) val
*   data_receivers: [DataReceivers](wallaroo-ent-data_receiver-DataReceivers) tag
*   c: [Connections](wallaroo-ent-network-Connections) tag
*   recovery_file_cleaner: [RecoveryFileCleaner](wallaroo-core-common-RecoveryFileCleaner) tag
*   stop_the_world_pause: [U64](builtin-U64) val

#### Returns

* [RouterRegistry](wallaroo-ent-router_registry-RouterRegistry) tag^

---

## Public Behaviours

### dispose

```pony
be dispose()
```

---

### application_ready_to_work

```pony
be application_ready_to_work()
```

---

### set_data_router

```pony
be set_data_router(
  dr: DataRouter val)
```
#### Parameters

*   dr: [DataRouter](wallaroo-core-topology-DataRouter) val

---

### set_pre_state_data

```pony
be set_pre_state_data(
  psd: Array[PreStateData val] val)
```
#### Parameters

*   psd: [Array](builtin-Array)\[[PreStateData](wallaroo-core-topology-PreStateData) val\] val

---

### set_partition_router

```pony
be set_partition_router(
  state_name: String val,
  pr: PartitionRouter val)
```
#### Parameters

*   state_name: [String](builtin-String) val
*   pr: [PartitionRouter](wallaroo-core-topology-PartitionRouter) val

---

### set_stateless_partition_router

```pony
be set_stateless_partition_router(
  partition_id: U128 val,
  pr: StatelessPartitionRouter val)
```
#### Parameters

*   partition_id: [U128](builtin-U128) val
*   pr: [StatelessPartitionRouter](wallaroo-core-topology-StatelessPartitionRouter) val

---

### set_omni_router

```pony
be set_omni_router(
  o: OmniRouter val)
```
#### Parameters

*   o: [OmniRouter](wallaroo-core-topology-OmniRouter) val

---

### set_event_log

```pony
be set_event_log(
  e: EventLog tag)
```
#### Parameters

*   e: [EventLog](wallaroo-ent-recovery-EventLog) tag

---

### register_disposable

```pony
be register_disposable(
  d: DisposableActor tag)
```
#### Parameters

*   d: [DisposableActor](builtin-DisposableActor) tag

---

### register_source

```pony
be register_source(
  source: Source tag)
```
#### Parameters

*   source: [Source](wallaroo-core-source-Source) tag

---

### register_source_listener

```pony
be register_source_listener(
  source_listener: SourceListener tag)
```
#### Parameters

*   source_listener: [SourceListener](wallaroo-core-source-SourceListener) tag

---

### register_data_channel_listener

```pony
be register_data_channel_listener(
  dchl: DataChannelListener tag)
```
#### Parameters

*   dchl: [DataChannelListener](wallaroo-core-data_channel-DataChannelListener) tag

---

### register_control_channel_listener

```pony
be register_control_channel_listener(
  cchl: TCPListener tag)
```
#### Parameters

*   cchl: [TCPListener](net-TCPListener) tag

---

### register_data_channel

```pony
be register_data_channel(
  dc: DataChannel tag)
```
#### Parameters

*   dc: [DataChannel](wallaroo-core-data_channel-DataChannel) tag

---

### register_partition_router_subscriber

```pony
be register_partition_router_subscriber(
  state_name: String val,
  sub: RouterUpdateable tag)
```
#### Parameters

*   state_name: [String](builtin-String) val
*   sub: [RouterUpdateable](wallaroo-core-common-RouterUpdateable) tag

---

### unregister_partition_router_subscriber

```pony
be unregister_partition_router_subscriber(
  state_name: String val,
  sub: RouterUpdateable tag)
```
#### Parameters

*   state_name: [String](builtin-String) val
*   sub: [RouterUpdateable](wallaroo-core-common-RouterUpdateable) tag

---

### register_stateless_partition_router_subscriber

```pony
be register_stateless_partition_router_subscriber(
  partition_id: U128 val,
  sub: RouterUpdateable tag)
```
#### Parameters

*   partition_id: [U128](builtin-U128) val
*   sub: [RouterUpdateable](wallaroo-core-common-RouterUpdateable) tag

---

### unregister_stateless_partition_router_subscriber

```pony
be unregister_stateless_partition_router_subscriber(
  partition_id: U128 val,
  sub: RouterUpdateable tag)
```
#### Parameters

*   partition_id: [U128](builtin-U128) val
*   sub: [RouterUpdateable](wallaroo-core-common-RouterUpdateable) tag

---

### register_omni_router_step

```pony
be register_omni_router_step(
  s: Step tag)
```
#### Parameters

*   s: [Step](wallaroo-core-topology-Step) tag

---

### register_boundaries

```pony
be register_boundaries(
  bs: HashMap[String val, OutgoingBoundary tag, HashEq[String val] val] val,
  bbs: HashMap[String val, OutgoingBoundaryBuilder val, HashEq[String val] val] val)
```
#### Parameters

*   bs: [HashMap](collections-HashMap)\[[String](builtin-String) val, [OutgoingBoundary](wallaroo-core-boundary-OutgoingBoundary) tag, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val
*   bbs: [HashMap](collections-HashMap)\[[String](builtin-String) val, [OutgoingBoundaryBuilder](wallaroo-core-boundary-OutgoingBoundaryBuilder) val, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val

---

### create_partition_routers_from_blueprints

```pony
be create_partition_routers_from_blueprints(
  partition_blueprints: HashMap[String val, PartitionRouterBlueprint val, HashEq[String val] val] val)
```
#### Parameters

*   partition_blueprints: [HashMap](collections-HashMap)\[[String](builtin-String) val, [PartitionRouterBlueprint](wallaroo-core-topology-PartitionRouterBlueprint) val, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val

---

### create_stateless_partition_routers_from_blueprints

```pony
be create_stateless_partition_routers_from_blueprints(
  partition_blueprints: HashMap[U128 val, StatelessPartitionRouterBlueprint val, HashEq[U128 val] val] val)
```
#### Parameters

*   partition_blueprints: [HashMap](collections-HashMap)\[[U128](builtin-U128) val, [StatelessPartitionRouterBlueprint](wallaroo-core-topology-StatelessPartitionRouterBlueprint) val, [HashEq](collections-HashEq)\[[U128](builtin-U128) val\] val\] val

---

### create_omni_router_from_blueprint

```pony
be create_omni_router_from_blueprint(
  omni_router_blueprint: OmniRouterBlueprint val,
  local_sinks: HashMap[U128 val, Consumer tag, HashEq[U128 val] val] val,
  lti: LocalTopologyInitializer tag)
```
#### Parameters

*   omni_router_blueprint: [OmniRouterBlueprint](wallaroo-core-topology-OmniRouterBlueprint) val
*   local_sinks: [HashMap](collections-HashMap)\[[U128](builtin-U128) val, [Consumer](wallaroo-core-common-Consumer) tag, [HashEq](collections-HashEq)\[[U128](builtin-U128) val\] val\] val
*   lti: [LocalTopologyInitializer](wallaroo-core-initialization-LocalTopologyInitializer) tag

---

### inform_joining_worker

```pony
be inform_joining_worker(
  conn: TCPConnection tag,
  worker: String val,
  worker_count: USize val,
  local_topology: LocalTopology val)
```
#### Parameters

*   conn: [TCPConnection](net-TCPConnection) tag
*   worker: [String](builtin-String) val
*   worker_count: [USize](builtin-USize) val
*   local_topology: [LocalTopology](wallaroo-core-initialization-LocalTopology) val

---

### inform_cluster_of_join

```pony
be inform_cluster_of_join()
```

---

### inform_worker_of_boundary_count

```pony
be inform_worker_of_boundary_count(
  target_worker: String val)
```
#### Parameters

*   target_worker: [String](builtin-String) val

---

### reconnect_source_boundaries

```pony
be reconnect_source_boundaries(
  target_worker: String val)
```
#### Parameters

*   target_worker: [String](builtin-String) val

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
  worker_names: Array[String val] val,
  conn: TCPConnection tag)
```
#### Parameters

*   worker_names: [Array](builtin-Array)\[[String](builtin-String) val\] val
*   conn: [TCPConnection](net-TCPConnection) tag

---

### rotate_log_file

Called when it's time to rotate the log file for the worker.
This will mute upstream, ack on all in-flight messages, then initiate a
log file rotation, followed by snapshotting of all states on the worker
to the new file, before unmuting upstream and resuming processing.


```pony
be rotate_log_file()
```

---

### begin_log_rotation

Start the log rotation and initiate snapshots.


```pony
be begin_log_rotation()
```

---

### rotation_complete

Called when rotation has copmleted and we should resume processing


```pony
be rotation_complete()
```

---

### joining_worker_initialized

When a joining worker has initialized its topology, it contacts all
current workers. This behavior is called when that control
message is received.


```pony
be joining_worker_initialized(
  worker: String val)
```
#### Parameters

*   worker: [String](builtin-String) val

---

### remote_migration_request

Only one worker is contacted by all joining workers to indicate that a
join is requested. That worker, when it's ready to begin step migration,
then sends a message to all other current workers, telling them to begin
migration to the joining workers as well. This behavior is called when
that message is received.


```pony
be remote_migration_request(
  new_workers: Array[String val] val)
```
#### Parameters

*   new_workers: [Array](builtin-Array)\[[String](builtin-String) val\] val

---

### resume_the_world

```pony
be resume_the_world()
```

---

### begin_migration

Begin partition migration


```pony
be begin_migration(
  target_workers: Array[String val] val)
```
#### Parameters

*   target_workers: [Array](builtin-Array)\[[String](builtin-String) val\] val

---

### begin_migration_of_all

Begin partition migration of *all* local stateful partition steps,
as part of a shrink-to-fit migration.


```pony
be begin_migration_of_all()
```

---

### step_migration_complete

Step with provided step id has been created on another worker.


```pony
be step_migration_complete(
  step_id: U128 val)
```
#### Parameters

*   step_id: [U128](builtin-U128) val

---

### remote_mute_request

A remote worker requests that we mute all sources and data channel.


```pony
be remote_mute_request(
  originating_worker: String val)
```
#### Parameters

*   originating_worker: [String](builtin-String) val

---

### remote_unmute_request

A remote worker requests that we unmute all sources and data channel.


```pony
be remote_unmute_request(
  originating_worker: String val)
```
#### Parameters

*   originating_worker: [String](builtin-String) val

---

### process_migrating_target_ack

Called when we receive a migration batch ack from the new worker
(i.e. migration target) indicating it's ready to receive data messages


```pony
be process_migrating_target_ack(
  target: String val)
```
#### Parameters

*   target: [String](builtin-String) val

---

### ack_migration_batch_complete

Called when a new (joining) worker needs to ack to worker sender_name that
it's ready to start receiving messages after migration


```pony
be ack_migration_batch_complete(
  sender_name: String val)
```
#### Parameters

*   sender_name: [String](builtin-String) val

---

### initiate_shrink

This should only be called on the worker contacted via an external
message to initiate a shrink.


```pony
be initiate_shrink(
  remaining_workers: Array[String val] val,
  leaving_workers: Array[String val] val)
```
#### Parameters

*   remaining_workers: [Array](builtin-Array)\[[String](builtin-String) val\] val
*   leaving_workers: [Array](builtin-Array)\[[String](builtin-String) val\] val

---

### prepare_shrink

One worker is contacted via external message to begin autoscale
shrink. That worker then informs every other worker to prepare for
shrink. This behavior is called in response to receiving that message
from the contacted worker.


```pony
be prepare_shrink(
  remaining_workers: Array[String val] val,
  leaving_workers: Array[String val] val)
```
#### Parameters

*   remaining_workers: [Array](builtin-Array)\[[String](builtin-String) val\] val
*   leaving_workers: [Array](builtin-Array)\[[String](builtin-String) val\] val

---

### begin_leaving_migration

This should only be called on a worker designated to leave the cluster
as part of shrink to fit.


```pony
be begin_leaving_migration(
  remaining_workers: Array[String val] val,
  leaving_workers: Array[String val] val)
```
#### Parameters

*   remaining_workers: [Array](builtin-Array)\[[String](builtin-String) val\] val
*   leaving_workers: [Array](builtin-Array)\[[String](builtin-String) val\] val

---

### disconnect_from_leaving_worker

```pony
be disconnect_from_leaving_worker(
  worker: String val)
```
#### Parameters

*   worker: [String](builtin-String) val

---

### add_state_proxy\[K: ([Hashable](collections-Hashable) val & [Equatable](builtin-Equatable)\[K\] val)\]

Called when a stateful step has been added to another worker


```pony
be add_state_proxy[K: (Hashable val & Equatable[K] val)](
  id: U128 val,
  proxy_address: ProxyAddress val,
  key: K,
  state_name: String val)
```
#### Parameters

*   id: [U128](builtin-U128) val
*   proxy_address: [ProxyAddress](wallaroo-core-topology-ProxyAddress) val
*   key: K
*   state_name: [String](builtin-String) val

---

### move_proxy_to_stateful_step\[K: ([Hashable](collections-Hashable) val & [Equatable](builtin-Equatable)\[K\] val)\]

Called when a stateful step has been migrated to this worker from another
worker


```pony
be move_proxy_to_stateful_step[K: (Hashable val & Equatable[K] val)](
  id: U128 val,
  target: Consumer tag,
  key: K,
  state_name: String val,
  source_worker: String val)
```
#### Parameters

*   id: [U128](builtin-U128) val
*   target: [Consumer](wallaroo-core-common-Consumer) tag
*   key: K
*   state_name: [String](builtin-String) val
*   source_worker: [String](builtin-String) val

---

## Public Functions

### migrate_onto_new_workers

Called when a new worker joins the cluster and we are ready to start
the partition migration process. We first trigger a pause to allow
in-flight messages to finish processing.


```pony
fun ref migrate_onto_new_workers(
  new_workers: Array[String val] val)
: None val
```
#### Parameters

*   new_workers: [Array](builtin-Array)\[[String](builtin-String) val\] val

#### Returns

* [None](builtin-None) val

---

### try_to_resume_processing_immediately

```pony
fun ref try_to_resume_processing_immediately()
: None val
```

#### Returns

* [None](builtin-None) val

---

### add_to_step_waiting_list

```pony
fun ref add_to_step_waiting_list(
  step_id: U128 val)
: None val
```
#### Parameters

*   step_id: [U128](builtin-U128) val

#### Returns

* [None](builtin-None) val

---

### move_stateful_step_to_proxy\[K: ([Hashable](collections-Hashable) val & [Equatable](builtin-Equatable)\[K\] val)\]

Called when a stateful step has been migrated off this worker to another
worker


```pony
fun ref move_stateful_step_to_proxy[K: (Hashable val & Equatable[K] val)](
  id: U128 val,
  proxy_address: ProxyAddress val,
  key: K,
  state_name: String val)
: None val
```
#### Parameters

*   id: [U128](builtin-U128) val
*   proxy_address: [ProxyAddress](wallaroo-core-topology-ProxyAddress) val
*   key: K
*   state_name: [String](builtin-String) val

#### Returns

* [None](builtin-None) val

---

## Private Functions

### _worker_count

```pony
fun box _worker_count()
: USize val
```

#### Returns

* [USize](builtin-USize) val

---

### _register_partition_router_subscriber

```pony
fun ref _register_partition_router_subscriber(
  state_name: String val,
  sub: RouterUpdateable tag)
: None val
```
#### Parameters

*   state_name: [String](builtin-String) val
*   sub: [RouterUpdateable](wallaroo-core-common-RouterUpdateable) tag

#### Returns

* [None](builtin-None) val

---

### _register_stateless_partition_router_subscriber

```pony
fun ref _register_stateless_partition_router_subscriber(
  partition_id: U128 val,
  sub: RouterUpdateable tag)
: None val
```
#### Parameters

*   partition_id: [U128](builtin-U128) val
*   sub: [RouterUpdateable](wallaroo-core-common-RouterUpdateable) tag

#### Returns

* [None](builtin-None) val

---

### _register_omni_router_step

```pony
fun ref _register_omni_router_step(
  s: Step tag)
: None val
```
#### Parameters

*   s: [Step](wallaroo-core-topology-Step) tag

#### Returns

* [None](builtin-None) val

---

### _distribute_data_router

```pony
fun box _distribute_data_router()
: None val
```

#### Returns

* [None](builtin-None) val

---

### _distribute_omni_router

```pony
fun box _distribute_omni_router()
: None val
```

#### Returns

* [None](builtin-None) val

---

### _distribute_partition_router

```pony
fun ref _distribute_partition_router(
  partition_router: PartitionRouter val)
: None val
```
#### Parameters

*   partition_router: [PartitionRouter](wallaroo-core-topology-PartitionRouter) val

#### Returns

* [None](builtin-None) val

---

### _distribute_stateless_partition_router

```pony
fun ref _distribute_stateless_partition_router(
  partition_router: StatelessPartitionRouter val)
: None val
```
#### Parameters

*   partition_router: [StatelessPartitionRouter](wallaroo-core-topology-StatelessPartitionRouter) val

#### Returns

* [None](builtin-None) val

---

### _distribute_boundary_removal

```pony
fun box _distribute_boundary_removal(
  worker: String val)
: None val
```
#### Parameters

*   worker: [String](builtin-String) val

#### Returns

* [None](builtin-None) val

---

### _distribute_boundary_builders

```pony
fun box _distribute_boundary_builders()
: None val
```

#### Returns

* [None](builtin-None) val

---

### _inform_cluster_of_join

```pony
fun ref _inform_cluster_of_join()
: None val
```

#### Returns

* [None](builtin-None) val

---

### _stop_the_world_for_log_rotation

We currently stop all message processing before perofrming log rotaion.


```pony
fun ref _stop_the_world_for_log_rotation()
: None val
```

#### Returns

* [None](builtin-None) val

---

### _stop_the_world

We currently stop all message processing before migrating partitions and
updating routers/routes.


```pony
fun ref _stop_the_world(
  new_workers: Array[String val] val)
: None val
```
#### Parameters

*   new_workers: [Array](builtin-Array)\[[String](builtin-String) val\] val

#### Returns

* [None](builtin-None) val

---

### _resume_the_world

Migration is complete and we're ready to resume message processing


```pony
fun ref _resume_the_world()
: None val
```

#### Returns

* [None](builtin-None) val

---

### _send_migration_batch_complete

Inform migration target that the entire migration batch has been sent.


```pony
fun box _send_migration_batch_complete()
: None val
```

#### Returns

* [None](builtin-None) val

---

### _send_leaving_worker_done_migrating

Inform migration target that the entire migration batch has been sent.


```pony
fun box _send_leaving_worker_done_migrating()
: None val
```

#### Returns

* [None](builtin-None) val

---

### _mute_request

```pony
fun ref _mute_request(
  originating_worker: String val)
: None val
```
#### Parameters

*   originating_worker: [String](builtin-String) val

#### Returns

* [None](builtin-None) val

---

### _unmute_request

```pony
fun ref _unmute_request(
  originating_worker: String val)
: None val
```
#### Parameters

*   originating_worker: [String](builtin-String) val

#### Returns

* [None](builtin-None) val

---

### _stop_all_local

Mute all sources and data channel.


```pony
fun box _stop_all_local()
: None val
```

#### Returns

* [None](builtin-None) val

---

### _resume_all_local

Unmute all sources and data channel.


```pony
fun box _resume_all_local()
: None val
```

#### Returns

* [None](builtin-None) val

---

### _migrate_partition_steps

Called to initiate migrating partition steps to a target worker in order
to rebalance.


```pony
fun ref _migrate_partition_steps(
  state_name: String val,
  target_workers: Array[String val] val)
: None val
```
#### Parameters

*   state_name: [String](builtin-String) val
*   target_workers: [Array](builtin-Array)\[[String](builtin-String) val\] val

#### Returns

* [None](builtin-None) val

---

### _migrate_all_partition_steps

Called to initiate migrating all partition steps the set of remaining
workers.


```pony
fun ref _migrate_all_partition_steps(
  state_name: String val,
  target_workers: Array[(String val , OutgoingBoundary tag)] val)
: None val
```
#### Parameters

*   state_name: [String](builtin-String) val
*   target_workers: [Array](builtin-Array)\[([String](builtin-String) val , [OutgoingBoundary](wallaroo-core-boundary-OutgoingBoundary) tag)\] val

#### Returns

* [None](builtin-None) val

---

### _prepare_shrink

```pony
fun ref _prepare_shrink(
  remaining_workers: Array[String val] val,
  leaving_workers: Array[String val] val)
: None val
```
#### Parameters

*   remaining_workers: [Array](builtin-Array)\[[String](builtin-String) val\] val
*   leaving_workers: [Array](builtin-Array)\[[String](builtin-String) val\] val

#### Returns

* [None](builtin-None) val

---

### _stop_the_world_for_shrink

We currently stop all message processing before migrating partitions and
updating routers/routes.


```pony
fun ref _stop_the_world_for_shrink()
: None val
```

#### Returns

* [None](builtin-None) val

---

### _move_step_to_proxy

Called when a step has been migrated off this worker to another worker


```pony
fun ref _move_step_to_proxy(
  id: U128 val,
  proxy_address: ProxyAddress val)
: None val
```
#### Parameters

*   id: [U128](builtin-U128) val
*   proxy_address: [ProxyAddress](wallaroo-core-topology-ProxyAddress) val

#### Returns

* [None](builtin-None) val

---

### _add_state_proxy_to_partition_router\[K: ([Hashable](collections-Hashable) val & [Equatable](builtin-Equatable)\[K\] val)\]

```pony
fun ref _add_state_proxy_to_partition_router[K: (Hashable val & Equatable[K] val)](
  proxy_address: ProxyAddress val,
  key: K,
  state_name: String val)
: None val
```
#### Parameters

*   proxy_address: [ProxyAddress](wallaroo-core-topology-ProxyAddress) val
*   key: K
*   state_name: [String](builtin-String) val

#### Returns

* [None](builtin-None) val

---

### _remove_step_from_data_router

```pony
fun ref _remove_step_from_data_router(
  id: U128 val)
: None val
```
#### Parameters

*   id: [U128](builtin-U128) val

#### Returns

* [None](builtin-None) val

---

### _add_proxy_to_omni_router

```pony
fun ref _add_proxy_to_omni_router(
  id: U128 val,
  proxy_address: ProxyAddress val)
: None val
```
#### Parameters

*   id: [U128](builtin-U128) val
*   proxy_address: [ProxyAddress](wallaroo-core-topology-ProxyAddress) val

#### Returns

* [None](builtin-None) val

---

### _move_proxy_to_step

Called when a step has been migrated to this worker from another worker


```pony
fun ref _move_proxy_to_step(
  id: U128 val,
  target: Consumer tag,
  source_worker: String val)
: None val
```
#### Parameters

*   id: [U128](builtin-U128) val
*   target: [Consumer](wallaroo-core-common-Consumer) tag
*   source_worker: [String](builtin-String) val

#### Returns

* [None](builtin-None) val

---

