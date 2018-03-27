# Cluster

A trait for sending messages to workers in the cluster.


```pony
trait tag Cluster
```

## Public Behaviours

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
  exclusions: Array[String val] val)
```
#### Parameters

*   exclusions: [Array](builtin-Array)\[[String](builtin-String) val\] val

---

### request_cluster_unmute

```pony
be request_cluster_unmute()
```

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

```pony
be ack_migration_batch_complete(
  ack_target: String val)
```
#### Parameters

*   ack_target: [String](builtin-String) val

---

