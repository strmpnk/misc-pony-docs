# ChannelMsgEncoder

```pony
primitive val ChannelMsgEncoder
```

## Constructors

### create

```pony
new val create()
: ChannelMsgEncoder val^
```

#### Returns

* [ChannelMsgEncoder](wallaroo-core-messages-ChannelMsgEncoder) val^

---

## Public Functions

### data_channel

```pony
fun box data_channel(
  delivery_msg: ReplayableDeliveryMsg val,
  pipeline_time_spent: U64 val,
  seq_id: U64 val,
  wb: Writer ref,
  auth: AmbientAuth val,
  latest_ts: U64 val,
  metrics_id: U16 val,
  metric_name: String val)
: Array[(String val | Array[U8 val] val)] val ?
```
#### Parameters

*   delivery_msg: [ReplayableDeliveryMsg](wallaroo-core-messages-ReplayableDeliveryMsg) val
*   pipeline_time_spent: [U64](builtin-U64) val
*   seq_id: [U64](builtin-U64) val
*   wb: [Writer](buffered-Writer) ref
*   auth: [AmbientAuth](builtin-AmbientAuth) val
*   latest_ts: [U64](builtin-U64) val
*   metrics_id: [U16](builtin-U16) val
*   metric_name: [String](builtin-String) val

#### Returns

* [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val ?

---

### migrate_step\[K: ([Hashable](collections-Hashable) val & [Equatable](builtin-Equatable)\[K\] val)\]

```pony
fun box migrate_step[K: (Hashable val & Equatable[K] val)](
  step_id: U128 val,
  state_name: String val,
  key: K,
  state: (String val | Array[U8 val] val),
  worker: String val,
  auth: AmbientAuth val)
: Array[(String val | Array[U8 val] val)] val ?
```
#### Parameters

*   step_id: [U128](builtin-U128) val
*   state_name: [String](builtin-String) val
*   key: K
*   state: ([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)
*   worker: [String](builtin-String) val
*   auth: [AmbientAuth](builtin-AmbientAuth) val

#### Returns

* [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val ?

---

### migration_batch_complete

Sent to signal to joining worker that a batch of steps has finished
emigrating from this step.


```pony
fun box migration_batch_complete(
  sender: String val,
  auth: AmbientAuth val)
: Array[(String val | Array[U8 val] val)] val ?
```
#### Parameters

*   sender: [String](builtin-String) val
*   auth: [AmbientAuth](builtin-AmbientAuth) val

#### Returns

* [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val ?

---

### ack_migration_batch_complete

Sent to ack that a batch of steps has finished immigrating to this step


```pony
fun box ack_migration_batch_complete(
  worker: String val,
  auth: AmbientAuth val)
: Array[(String val | Array[U8 val] val)] val ?
```
#### Parameters

*   worker: [String](builtin-String) val
*   auth: [AmbientAuth](builtin-AmbientAuth) val

#### Returns

* [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val ?

---

### step_migration_complete

Sent when the migration of step step_id is complete


```pony
fun box step_migration_complete(
  step_id: U128 val,
  auth: AmbientAuth val)
: Array[(String val | Array[U8 val] val)] val ?
```
#### Parameters

*   step_id: [U128](builtin-U128) val
*   auth: [AmbientAuth](builtin-AmbientAuth) val

#### Returns

* [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val ?

---

### begin_leaving_migration

This message is sent by the current worker coordinating autoscale shrink to
all leaving workers once all in-flight messages have finished processing
after stopping the world. At that point, it's safe for leaving workers to
migrate steps to the remaining workers.


```pony
fun box begin_leaving_migration(
  remaining_workers: Array[String val] val,
  leaving_workers: Array[String val] val,
  auth: AmbientAuth val)
: Array[(String val | Array[U8 val] val)] val ?
```
#### Parameters

*   remaining_workers: [Array](builtin-Array)\[[String](builtin-String) val\] val
*   leaving_workers: [Array](builtin-Array)\[[String](builtin-String) val\] val
*   auth: [AmbientAuth](builtin-AmbientAuth) val

#### Returns

* [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val ?

---

### initiate_shrink

```pony
fun box initiate_shrink(
  remaining_workers: Array[String val] val,
  leaving_workers: Array[String val] val,
  auth: AmbientAuth val)
: Array[(String val | Array[U8 val] val)] val ?
```
#### Parameters

*   remaining_workers: [Array](builtin-Array)\[[String](builtin-String) val\] val
*   leaving_workers: [Array](builtin-Array)\[[String](builtin-String) val\] val
*   auth: [AmbientAuth](builtin-AmbientAuth) val

#### Returns

* [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val ?

---

### prepare_shrink

The worker initially contacted for autoscale shrink sends this message to
all other remaining workers so they can prepare for the shrink event.


```pony
fun box prepare_shrink(
  remaining_workers: Array[String val] val,
  leaving_workers: Array[String val] val,
  auth: AmbientAuth val)
: Array[(String val | Array[U8 val] val)] val ?
```
#### Parameters

*   remaining_workers: [Array](builtin-Array)\[[String](builtin-String) val\] val
*   leaving_workers: [Array](builtin-Array)\[[String](builtin-String) val\] val
*   auth: [AmbientAuth](builtin-AmbientAuth) val

#### Returns

* [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val ?

---

### mute_request

```pony
fun box mute_request(
  originating_worker: String val,
  auth: AmbientAuth val)
: Array[(String val | Array[U8 val] val)] val ?
```
#### Parameters

*   originating_worker: [String](builtin-String) val
*   auth: [AmbientAuth](builtin-AmbientAuth) val

#### Returns

* [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val ?

---

### unmute_request

```pony
fun box unmute_request(
  originating_worker: String val,
  auth: AmbientAuth val)
: Array[(String val | Array[U8 val] val)] val ?
```
#### Parameters

*   originating_worker: [String](builtin-String) val
*   auth: [AmbientAuth](builtin-AmbientAuth) val

#### Returns

* [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val ?

---

### delivery\[D: [Any](builtin-Any) val\]

```pony
fun box delivery[D: Any val](
  target_id: U128 val,
  from_worker_name: String val,
  msg_data: D,
  metric_name: String val,
  auth: AmbientAuth val,
  proxy_address: ProxyAddress val,
  msg_uid: U128 val,
  frac_ids: (Array[U32 val] val | None val))
: Array[(String val | Array[U8 val] val)] val ?
```
#### Parameters

*   target_id: [U128](builtin-U128) val
*   from_worker_name: [String](builtin-String) val
*   msg_data: D
*   metric_name: [String](builtin-String) val
*   auth: [AmbientAuth](builtin-AmbientAuth) val
*   proxy_address: [ProxyAddress](wallaroo-core-topology-ProxyAddress) val
*   msg_uid: [U128](builtin-U128) val
*   frac_ids: ([Array](builtin-Array)\[[U32](builtin-U32) val\] val | [None](builtin-None) val)

#### Returns

* [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val ?

---

### identify_control_port

```pony
fun box identify_control_port(
  worker_name: String val,
  service: String val,
  auth: AmbientAuth val)
: Array[(String val | Array[U8 val] val)] val ?
```
#### Parameters

*   worker_name: [String](builtin-String) val
*   service: [String](builtin-String) val
*   auth: [AmbientAuth](builtin-AmbientAuth) val

#### Returns

* [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val ?

---

### identify_data_port

```pony
fun box identify_data_port(
  worker_name: String val,
  service: String val,
  auth: AmbientAuth val)
: Array[(String val | Array[U8 val] val)] val ?
```
#### Parameters

*   worker_name: [String](builtin-String) val
*   service: [String](builtin-String) val
*   auth: [AmbientAuth](builtin-AmbientAuth) val

#### Returns

* [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val ?

---

### reconnect_data_port

```pony
fun box reconnect_data_port(
  worker_name: String val,
  auth: AmbientAuth val)
: Array[(String val | Array[U8 val] val)] val ?
```
#### Parameters

*   worker_name: [String](builtin-String) val
*   auth: [AmbientAuth](builtin-AmbientAuth) val

#### Returns

* [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val ?

---

### spin_up_local_topology

```pony
fun box spin_up_local_topology(
  local_topology: LocalTopology val,
  auth: AmbientAuth val)
: Array[(String val | Array[U8 val] val)] val ?
```
#### Parameters

*   local_topology: [LocalTopology](wallaroo-core-initialization-LocalTopology) val
*   auth: [AmbientAuth](builtin-AmbientAuth) val

#### Returns

* [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val ?

---

### spin_up_step

```pony
fun box spin_up_step(
  step_id: U64 val,
  step_builder: StepBuilder val,
  auth: AmbientAuth val)
: Array[(String val | Array[U8 val] val)] val ?
```
#### Parameters

*   step_id: [U64](builtin-U64) val
*   step_builder: [StepBuilder](wallaroo-core-topology-StepBuilder) val
*   auth: [AmbientAuth](builtin-AmbientAuth) val

#### Returns

* [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val ?

---

### topology_ready

```pony
fun box topology_ready(
  worker_name: String val,
  auth: AmbientAuth val)
: Array[(String val | Array[U8 val] val)] val ?
```
#### Parameters

*   worker_name: [String](builtin-String) val
*   auth: [AmbientAuth](builtin-AmbientAuth) val

#### Returns

* [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val ?

---

### create_connections

```pony
fun box create_connections(
  c_addrs: HashMap[String val, (String val , String val), HashEq[String val] val] val,
  d_addrs: HashMap[String val, (String val , String val), HashEq[String val] val] val,
  auth: AmbientAuth val)
: Array[(String val | Array[U8 val] val)] val ?
```
#### Parameters

*   c_addrs: [HashMap](collections-HashMap)\[[String](builtin-String) val, ([String](builtin-String) val , [String](builtin-String) val), [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val
*   d_addrs: [HashMap](collections-HashMap)\[[String](builtin-String) val, ([String](builtin-String) val , [String](builtin-String) val), [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val
*   auth: [AmbientAuth](builtin-AmbientAuth) val

#### Returns

* [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val ?

---

### connections_ready

```pony
fun box connections_ready(
  worker_name: String val,
  auth: AmbientAuth val)
: Array[(String val | Array[U8 val] val)] val ?
```
#### Parameters

*   worker_name: [String](builtin-String) val
*   auth: [AmbientAuth](builtin-AmbientAuth) val

#### Returns

* [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val ?

---

### create_data_channel_listener

```pony
fun box create_data_channel_listener(
  workers: Array[String val] val,
  auth: AmbientAuth val)
: Array[(String val | Array[U8 val] val)] val ?
```
#### Parameters

*   workers: [Array](builtin-Array)\[[String](builtin-String) val\] val
*   auth: [AmbientAuth](builtin-AmbientAuth) val

#### Returns

* [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val ?

---

### data_connect

```pony
fun box data_connect(
  sender_name: String val,
  sender_step_id: U128 val,
  auth: AmbientAuth val)
: Array[(String val | Array[U8 val] val)] val ?
```
#### Parameters

*   sender_name: [String](builtin-String) val
*   sender_step_id: [U128](builtin-U128) val
*   auth: [AmbientAuth](builtin-AmbientAuth) val

#### Returns

* [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val ?

---

### ack_data_connect

```pony
fun box ack_data_connect(
  last_id_seen: U64 val,
  auth: AmbientAuth val)
: Array[(String val | Array[U8 val] val)] val ?
```
#### Parameters

*   last_id_seen: [U64](builtin-U64) val
*   auth: [AmbientAuth](builtin-AmbientAuth) val

#### Returns

* [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val ?

---

### data_disconnect

```pony
fun box data_disconnect(
  auth: AmbientAuth val)
: Array[(String val | Array[U8 val] val)] val ?
```
#### Parameters

*   auth: [AmbientAuth](builtin-AmbientAuth) val

#### Returns

* [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val ?

---

### start_normal_data_sending

```pony
fun box start_normal_data_sending(
  last_id_seen: U64 val,
  auth: AmbientAuth val)
: Array[(String val | Array[U8 val] val)] val ?
```
#### Parameters

*   last_id_seen: [U64](builtin-U64) val
*   auth: [AmbientAuth](builtin-AmbientAuth) val

#### Returns

* [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val ?

---

### replay_complete

```pony
fun box replay_complete(
  sender_name: String val,
  boundary_id: U128 val,
  auth: AmbientAuth val)
: Array[(String val | Array[U8 val] val)] val ?
```
#### Parameters

*   sender_name: [String](builtin-String) val
*   boundary_id: [U128](builtin-U128) val
*   auth: [AmbientAuth](builtin-AmbientAuth) val

#### Returns

* [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val ?

---

### ack_watermark

```pony
fun box ack_watermark(
  sender_name: String val,
  sender_step_id: U128 val,
  seq_id: U64 val,
  auth: AmbientAuth val)
: Array[(String val | Array[U8 val] val)] val ?
```
#### Parameters

*   sender_name: [String](builtin-String) val
*   sender_step_id: [U128](builtin-U128) val
*   seq_id: [U64](builtin-U64) val
*   auth: [AmbientAuth](builtin-AmbientAuth) val

#### Returns

* [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val ?

---

### replay

```pony
fun box replay(
  delivery_bytes: Array[(String val | Array[U8 val] val)] val,
  auth: AmbientAuth val)
: Array[(String val | Array[U8 val] val)] val ?
```
#### Parameters

*   delivery_bytes: [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val
*   auth: [AmbientAuth](builtin-AmbientAuth) val

#### Returns

* [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val ?

---

### join_cluster

This message is sent from a worker requesting to join a running cluster to
any existing worker in the cluster.


```pony
fun box join_cluster(
  worker_name: String val,
  worker_count: USize val,
  auth: AmbientAuth val)
: Array[(String val | Array[U8 val] val)] val ?
```
#### Parameters

*   worker_name: [String](builtin-String) val
*   worker_count: [USize](builtin-USize) val
*   auth: [AmbientAuth](builtin-AmbientAuth) val

#### Returns

* [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val ?

---

### inform_joining_worker

This message is sent as a response to a JoinCluster message. Currently it
only informs the new worker of metrics-related info


```pony
fun box inform_joining_worker(
  worker_name: String val,
  metric_app_name: String val,
  l_topology: LocalTopology val,
  metric_host: String val,
  metric_service: String val,
  control_addrs: HashMap[String val, (String val , String val), HashEq[String val] val] val,
  data_addrs: HashMap[String val, (String val , String val), HashEq[String val] val] val,
  worker_names: Array[String val] val,
  partition_blueprints: HashMap[String val, PartitionRouterBlueprint val, HashEq[String val] val] val,
  stateless_partition_blueprints: HashMap[U128 val, StatelessPartitionRouterBlueprint val, HashEq[U128 val] val] val,
  omni_router_blueprint: OmniRouterBlueprint val,
  auth: AmbientAuth val)
: Array[(String val | Array[U8 val] val)] val ?
```
#### Parameters

*   worker_name: [String](builtin-String) val
*   metric_app_name: [String](builtin-String) val
*   l_topology: [LocalTopology](wallaroo-core-initialization-LocalTopology) val
*   metric_host: [String](builtin-String) val
*   metric_service: [String](builtin-String) val
*   control_addrs: [HashMap](collections-HashMap)\[[String](builtin-String) val, ([String](builtin-String) val , [String](builtin-String) val), [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val
*   data_addrs: [HashMap](collections-HashMap)\[[String](builtin-String) val, ([String](builtin-String) val , [String](builtin-String) val), [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val
*   worker_names: [Array](builtin-Array)\[[String](builtin-String) val\] val
*   partition_blueprints: [HashMap](collections-HashMap)\[[String](builtin-String) val, [PartitionRouterBlueprint](wallaroo-core-topology-PartitionRouterBlueprint) val, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val
*   stateless_partition_blueprints: [HashMap](collections-HashMap)\[[U128](builtin-U128) val, [StatelessPartitionRouterBlueprint](wallaroo-core-topology-StatelessPartitionRouterBlueprint) val, [HashEq](collections-HashEq)\[[U128](builtin-U128) val\] val\] val
*   omni_router_blueprint: [OmniRouterBlueprint](wallaroo-core-topology-OmniRouterBlueprint) val
*   auth: [AmbientAuth](builtin-AmbientAuth) val

#### Returns

* [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val ?

---

### inform_join_error

This message is sent as a response to a JoinCluster message when there is
a join error and the joiner should shut down.


```pony
fun box inform_join_error(
  msg: String val,
  auth: AmbientAuth val)
: Array[(String val | Array[U8 val] val)] val ?
```
#### Parameters

*   msg: [String](builtin-String) val
*   auth: [AmbientAuth](builtin-AmbientAuth) val

#### Returns

* [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val ?

---

### inform_recover_not_join

This message is sent as a response to a JoinCluster message when we
already know the worker name (which indicates that it is recovering, not
joining)


```pony
fun box inform_recover_not_join(
  auth: AmbientAuth val)
: Array[(String val | Array[U8 val] val)] val ?
```
#### Parameters

*   auth: [AmbientAuth](builtin-AmbientAuth) val

#### Returns

* [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val ?

---

### joining_worker_initialized

This message is sent after a joining worker uses partition blueprints and
other topology information to initialize its topology. It indicates that
it is ready to receive migrated steps.


```pony
fun box joining_worker_initialized(
  worker_name: String val,
  c_addr: (String val , String val),
  d_addr: (String val , String val),
  auth: AmbientAuth val)
: Array[(String val | Array[U8 val] val)] val ?
```
#### Parameters

*   worker_name: [String](builtin-String) val
*   c_addr: ([String](builtin-String) val , [String](builtin-String) val)
*   d_addr: ([String](builtin-String) val , [String](builtin-String) val)
*   auth: [AmbientAuth](builtin-AmbientAuth) val

#### Returns

* [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val ?

---

### initiate_join_migration

One worker is contacted by all joining workers and initially coordinates
state migration to those workers. When it is ready to migrate steps, it
sends this message to every other current worker informing them to begin
migration as well.


```pony
fun box initiate_join_migration(
  new_workers: Array[String val] val,
  auth: AmbientAuth val)
: Array[(String val | Array[U8 val] val)] val ?
```
#### Parameters

*   new_workers: [Array](builtin-Array)\[[String](builtin-String) val\] val
*   auth: [AmbientAuth](builtin-AmbientAuth) val

#### Returns

* [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val ?

---

### leaving_worker_done_migrating

A leaving worker sends this to indicate it has migrated all steps back to
remaining workers.


```pony
fun box leaving_worker_done_migrating(
  worker_name: String val,
  auth: AmbientAuth val)
: Array[(String val | Array[U8 val] val)] val ?
```
#### Parameters

*   worker_name: [String](builtin-String) val
*   auth: [AmbientAuth](builtin-AmbientAuth) val

#### Returns

* [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val ?

---

### request_boundary_count

```pony
fun box request_boundary_count(
  sender: String val,
  auth: AmbientAuth val)
: Array[(String val | Array[U8 val] val)] val ?
```
#### Parameters

*   sender: [String](builtin-String) val
*   auth: [AmbientAuth](builtin-AmbientAuth) val

#### Returns

* [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val ?

---

### replay_boundary_count

```pony
fun box replay_boundary_count(
  sender: String val,
  count: USize val,
  auth: AmbientAuth val)
: Array[(String val | Array[U8 val] val)] val ?
```
#### Parameters

*   sender: [String](builtin-String) val
*   count: [USize](builtin-USize) val
*   auth: [AmbientAuth](builtin-AmbientAuth) val

#### Returns

* [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val ?

---

### announce_new_stateful_step\[K: ([Hashable](collections-Hashable) val & [Equatable](builtin-Equatable)\[K\] val)\]

This message is sent to notify another worker that a new stateful step
has been created on this worker and that partition routers should be
updated.


```pony
fun box announce_new_stateful_step[K: (Hashable val & Equatable[K] val)](
  id: U128 val,
  worker_name: String val,
  key: K,
  state_name: String val,
  auth: AmbientAuth val)
: Array[(String val | Array[U8 val] val)] val ?
```
#### Parameters

*   id: [U128](builtin-U128) val
*   worker_name: [String](builtin-String) val
*   key: K
*   state_name: [String](builtin-String) val
*   auth: [AmbientAuth](builtin-AmbientAuth) val

#### Returns

* [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val ?

---

### rotate_log_files

```pony
fun box rotate_log_files(
  auth: AmbientAuth val)
: Array[(String val | Array[U8 val] val)] val ?
```
#### Parameters

*   auth: [AmbientAuth](builtin-AmbientAuth) val

#### Returns

* [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val ?

---

### clean_shutdown

```pony
fun box clean_shutdown(
  auth: AmbientAuth val,
  msg: String val = seq)
: Array[(String val | Array[U8 val] val)] val ?
```
#### Parameters

*   auth: [AmbientAuth](builtin-AmbientAuth) val
*   msg: [String](builtin-String) val = seq

#### Returns

* [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val ?

---

### eq

```pony
fun box eq(
  that: ChannelMsgEncoder val)
: Bool val
```
#### Parameters

*   that: [ChannelMsgEncoder](wallaroo-core-messages-ChannelMsgEncoder) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: ChannelMsgEncoder val)
: Bool val
```
#### Parameters

*   that: [ChannelMsgEncoder](wallaroo-core-messages-ChannelMsgEncoder) val

#### Returns

* [Bool](builtin-Bool) val

---

## Private Functions

### _encode

```pony
fun box _encode(
  msg: ChannelMsg val,
  auth: AmbientAuth val,
  wb: Writer ref = seq)
: Array[(String val | Array[U8 val] val)] val ?
```
#### Parameters

*   msg: [ChannelMsg](wallaroo-core-messages-ChannelMsg) val
*   auth: [AmbientAuth](builtin-AmbientAuth) val
*   wb: [Writer](buffered-Writer) ref = seq

#### Returns

* [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val ?

---

