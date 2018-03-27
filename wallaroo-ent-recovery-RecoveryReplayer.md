# RecoveryReplayer

Phases (if on a recovering worker):
  1) _AwaitingRecoveryReplayStart: Wait for start_recovery_replay() to be
     called. We only enter this phase if we are in recovery mode. Otherwise,
     we go immediately to _ReadyForNormalProcessing.
  2) _WaitingForBoundaryCounts: Wait for every running worker to inform this
     worker of how many boundaries they have incoming to us. We use these
     counts to determine when every incoming boundary has reconnected.
  3) _WaitForReconnections: Wait for every incoming boundary to reconnect.
     If all incoming boundaries are already connected by the time this
     phase begins, immediately move to next phase.
  4) _Replay: Wait for every boundary to send a message indicating replay
     is finished, at which point we can clear deduplication lists and
     inform other workers that they are free to send normal messages.
  5) _ReadyForNormalProcessing: Finished replay

ASSUMPTION: Recovery replay can happen at most once in the lifecycle of a
  worker.


```pony
actor tag RecoveryReplayer
```

## Constructors

### create

```pony
new tag create(
  auth: AmbientAuth val,
  worker_name: String val,
  data_receivers: DataReceivers tag,
  router_registry: RouterRegistry tag,
  cluster: Cluster tag,
  is_recovering: Bool val = seq)
: RecoveryReplayer tag^
```
#### Parameters

*   auth: [AmbientAuth](builtin-AmbientAuth) val
*   worker_name: [String](builtin-String) val
*   data_receivers: [DataReceivers](wallaroo-ent-data_receiver-DataReceivers) tag
*   router_registry: [RouterRegistry](wallaroo-ent-router_registry-RouterRegistry) tag
*   cluster: [Cluster](wallaroo-ent-network-Cluster) tag
*   is_recovering: [Bool](builtin-Bool) val = seq

#### Returns

* [RecoveryReplayer](wallaroo-ent-recovery-RecoveryReplayer) tag^

---

## Public Behaviours

### register_step

```pony
be register_step(
  step: Step tag)
```
#### Parameters

*   step: [Step](wallaroo-core-topology-Step) tag

---

### add_expected_boundary_count

```pony
be add_expected_boundary_count(
  worker: String val,
  count: USize val)
```
#### Parameters

*   worker: [String](builtin-String) val
*   count: [USize](builtin-USize) val

---

### data_receiver_added

```pony
be data_receiver_added(
  worker: String val,
  boundary_step_id: U128 val,
  dr: DataReceiver tag)
```
#### Parameters

*   worker: [String](builtin-String) val
*   boundary_step_id: [U128](builtin-U128) val
*   dr: [DataReceiver](wallaroo-ent-data_receiver-DataReceiver) tag

---

### add_boundary_replay_complete

```pony
be add_boundary_replay_complete(
  worker: String val,
  boundary_id: U128 val)
```
#### Parameters

*   worker: [String](builtin-String) val
*   boundary_id: [U128](builtin-U128) val

---

### start_recovery_replay

```pony
be start_recovery_replay(
  workers: Array[String val] val,
  recovery: Recovery tag)
```
#### Parameters

*   workers: [Array](builtin-Array)\[[String](builtin-String) val\] val
*   recovery: [Recovery](wallaroo-ent-recovery-Recovery) tag

---

## Public Functions

### single_worker

```pony
fun box single_worker(
  workers: Array[String val] val)
: Bool val
```
#### Parameters

*   workers: [Array](builtin-Array)\[[String](builtin-String) val\] val

#### Returns

* [Bool](builtin-Bool) val

---

## Private Functions

### _print_replay_phase_error

```pony
fun box _print_replay_phase_error()
: None val
```

#### Returns

* [None](builtin-None) val

---

### _boundary_reconnected

```pony
fun ref _boundary_reconnected(
  worker: String val,
  boundary_step_id: U128 val)
: None val
```
#### Parameters

*   worker: [String](builtin-String) val
*   boundary_step_id: [U128](builtin-U128) val

#### Returns

* [None](builtin-None) val

---

### _wait_for_reconnections

```pony
fun ref _wait_for_reconnections(
  expected_boundaries: HashMap[String val, USize val, HashEq[String val] val] box,
  reconnected_boundaries: HashMap[String val, HashSet[U128 val, HashIs[U128 val] val] ref, HashEq[String val] val] ref)
: None val
```
#### Parameters

*   expected_boundaries: [HashMap](collections-HashMap)\[[String](builtin-String) val, [USize](builtin-USize) val, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] box
*   reconnected_boundaries: [HashMap](collections-HashMap)\[[String](builtin-String) val, [HashSet](collections-HashSet)\[[U128](builtin-U128) val, [HashIs](collections-HashIs)\[[U128](builtin-U128) val\] val\] ref, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] ref

#### Returns

* [None](builtin-None) val

---

### _start_replay_phase

```pony
fun ref _start_replay_phase(
  expected_boundaries: HashMap[String val, USize val, HashEq[String val] val] box)
: None val
```
#### Parameters

*   expected_boundaries: [HashMap](collections-HashMap)\[[String](builtin-String) val, [USize](builtin-USize) val, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] box

#### Returns

* [None](builtin-None) val

---

### _end_replay_phase

```pony
fun ref _end_replay_phase()
: None val
```

#### Returns

* [None](builtin-None) val

---

### _clear_deduplication_lists

```pony
fun ref _clear_deduplication_lists()
: None val
```

#### Returns

* [None](builtin-None) val

---

