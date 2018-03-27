# PartitionRebalancer

```pony
primitive val PartitionRebalancer
```

## Constructors

### create

```pony
new val create()
: PartitionRebalancer val^
```

#### Returns

* [PartitionRebalancer](wallaroo-ent-rebalancing-PartitionRebalancer) val^

---

## Public Functions

### step_counts_to_send

Calculate how many steps a worker should send based on the total steps
in the partition, the portion of those steps on the sending worker,
the current count of workers, and the number of joining workers.

The aim of this algorithm is to have a roughly equal number of steps on
each worker.  Returns the total amount to send and a list of how many
to send to each worker.


```pony
fun box step_counts_to_send(
  total_steps: USize val,
  worker_portion: USize val,
  current_workers_count: USize val,
  joining_worker_count: USize val)
: (USize val , Array[USize val] val)
```
#### Parameters

*   total_steps: [USize](builtin-USize) val
*   worker_portion: [USize](builtin-USize) val
*   current_workers_count: [USize](builtin-USize) val
*   joining_worker_count: [USize](builtin-USize) val

#### Returns

* ([USize](builtin-USize) val , [Array](builtin-Array)\[[USize](builtin-USize) val\] val)

---

### step_counts_to_send_on_leaving

```pony
fun box step_counts_to_send_on_leaving(
  total_steps: USize val,
  remaining_workers_count: USize val)
: Array[USize val] val
```
#### Parameters

*   total_steps: [USize](builtin-USize) val
*   remaining_workers_count: [USize](builtin-USize) val

#### Returns

* [Array](builtin-Array)\[[USize](builtin-USize) val\] val

---

### eq

```pony
fun box eq(
  that: PartitionRebalancer val)
: Bool val
```
#### Parameters

*   that: [PartitionRebalancer](wallaroo-ent-rebalancing-PartitionRebalancer) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: PartitionRebalancer val)
: Bool val
```
#### Parameters

*   that: [PartitionRebalancer](wallaroo-ent-rebalancing-PartitionRebalancer) val

#### Returns

* [Bool](builtin-Bool) val

---

