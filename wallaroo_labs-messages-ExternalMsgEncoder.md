# ExternalMsgEncoder

```pony
primitive val ExternalMsgEncoder
```

## Constructors

### create

```pony
new val create()
: ExternalMsgEncoder val^
```

#### Returns

* [ExternalMsgEncoder](wallaroo_labs-messages-ExternalMsgEncoder) val^

---

## Public Functions

### print_message

```pony
fun box print_message(
  message: String val,
  wb: Writer ref = seq)
: Array[(String val | Array[U8 val] val)] val
```
#### Parameters

*   message: [String](builtin-String) val
*   wb: [Writer](buffered-Writer) ref = seq

#### Returns

* [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val

---

### rotate_log

```pony
fun box rotate_log(
  worker_name: String val,
  wb: Writer ref = seq)
: Array[(String val | Array[U8 val] val)] val
```
#### Parameters

*   worker_name: [String](builtin-String) val
*   wb: [Writer](buffered-Writer) ref = seq

#### Returns

* [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val

---

### clean_shutdown

```pony
fun box clean_shutdown(
  msg: String val = seq,
  wb: Writer ref = seq)
: Array[(String val | Array[U8 val] val)] val
```
#### Parameters

*   msg: [String](builtin-String) val = seq
*   wb: [Writer](buffered-Writer) ref = seq

#### Returns

* [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val

---

### shrink_request

```pony
fun box shrink_request(
  query: Bool val,
  node_names: Array[String val] val = seq,
  num_nodes: U64 val = seq,
  wb: Writer ref = seq)
: Array[(String val | Array[U8 val] val)] val
```
#### Parameters

*   query: [Bool](builtin-Bool) val
*   node_names: [Array](builtin-Array)\[[String](builtin-String) val\] val = seq
*   num_nodes: [U64](builtin-U64) val = seq
*   wb: [Writer](buffered-Writer) ref = seq

#### Returns

* [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val

---

### shrink_query_response

```pony
fun box shrink_query_response(
  node_names: Array[String val] val = seq,
  num_nodes: U64 val = seq,
  wb: Writer ref = seq)
: Array[(String val | Array[U8 val] val)] val
```
#### Parameters

*   node_names: [Array](builtin-Array)\[[String](builtin-String) val\] val = seq
*   num_nodes: [U64](builtin-U64) val = seq
*   wb: [Writer](buffered-Writer) ref = seq

#### Returns

* [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val

---

### shrink_error_response

```pony
fun box shrink_error_response(
  message: String val,
  wb: Writer ref = seq)
: Array[(String val | Array[U8 val] val)] val
```
#### Parameters

*   message: [String](builtin-String) val
*   wb: [Writer](buffered-Writer) ref = seq

#### Returns

* [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val

---

### partition_query

A message requesting the current distribution of partition steps across
workers (organized by partition type and partition name).


```pony
fun box partition_query(
  wb: Writer ref = seq)
: Array[(String val | Array[U8 val] val)] val
```
#### Parameters

*   wb: [Writer](buffered-Writer) ref = seq

#### Returns

* [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val

---

### partition_query_response

```pony
fun box partition_query_response(
  state_routers: HashMap[String val, PartitionRouter val, HashEq[String val] val] ref,
  stateless_routers: HashMap[U128 val, StatelessPartitionRouter val, HashEq[U128 val] val] ref,
  wb: Writer ref = seq)
: Array[(String val | Array[U8 val] val)] val
```
#### Parameters

*   state_routers: [HashMap](collections-HashMap)\[[String](builtin-String) val, [PartitionRouter](wallaroo-core-topology-PartitionRouter) val, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] ref
*   stateless_routers: [HashMap](collections-HashMap)\[[U128](builtin-U128) val, [StatelessPartitionRouter](wallaroo-core-topology-StatelessPartitionRouter) val, [HashEq](collections-HashEq)\[[U128](builtin-U128) val\] val\] ref
*   wb: [Writer](buffered-Writer) ref = seq

#### Returns

* [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val

---

### cluster_status_query

A message requesting current cluster status. How many workers? What are
the worker names? Is the cluster currently processing messages (i.e. not
in a stop the world phase)?


```pony
fun box cluster_status_query(
  wb: Writer ref = seq)
: Array[(String val | Array[U8 val] val)] val
```
#### Parameters

*   wb: [Writer](buffered-Writer) ref = seq

#### Returns

* [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val

---

### cluster_status_query_response

```pony
fun box cluster_status_query_response(
  worker_count: USize val,
  worker_names: Array[String val] val,
  stop_the_world_in_process: Bool val,
  wb: Writer ref = seq)
: Array[(String val | Array[U8 val] val)] val
```
#### Parameters

*   worker_count: [USize](builtin-USize) val
*   worker_names: [Array](builtin-Array)\[[String](builtin-String) val\] val
*   stop_the_world_in_process: [Bool](builtin-Bool) val
*   wb: [Writer](buffered-Writer) ref = seq

#### Returns

* [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val

---

### partition_count_query

A message requesting the current count of partition steps across
workers (organized by partition type and partition name).


```pony
fun box partition_count_query(
  wb: Writer ref = seq)
: Array[(String val | Array[U8 val] val)] val
```
#### Parameters

*   wb: [Writer](buffered-Writer) ref = seq

#### Returns

* [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val

---

### partition_count_query_response

```pony
fun box partition_count_query_response(
  state_routers: HashMap[String val, PartitionRouter val, HashEq[String val] val] ref,
  stateless_routers: HashMap[U128 val, StatelessPartitionRouter val, HashEq[U128 val] val] ref,
  wb: Writer ref = seq)
: Array[(String val | Array[U8 val] val)] val
```
#### Parameters

*   state_routers: [HashMap](collections-HashMap)\[[String](builtin-String) val, [PartitionRouter](wallaroo-core-topology-PartitionRouter) val, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] ref
*   stateless_routers: [HashMap](collections-HashMap)\[[U128](builtin-U128) val, [StatelessPartitionRouter](wallaroo-core-topology-StatelessPartitionRouter) val, [HashEq](collections-HashEq)\[[U128](builtin-U128) val\] val\] ref
*   wb: [Writer](buffered-Writer) ref = seq

#### Returns

* [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val

---

### eq

```pony
fun box eq(
  that: ExternalMsgEncoder val)
: Bool val
```
#### Parameters

*   that: [ExternalMsgEncoder](wallaroo_labs-messages-ExternalMsgEncoder) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: ExternalMsgEncoder val)
: Bool val
```
#### Parameters

*   that: [ExternalMsgEncoder](wallaroo_labs-messages-ExternalMsgEncoder) val

#### Returns

* [Bool](builtin-Bool) val

---

## Private Functions

### _encode

```pony
fun box _encode(
  id: U16 val,
  s: String val,
  wb: Writer ref)
: Array[(String val | Array[U8 val] val)] val
```
#### Parameters

*   id: [U16](builtin-U16) val
*   s: [String](builtin-String) val
*   wb: [Writer](buffered-Writer) ref

#### Returns

* [Array](builtin-Array)\[([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)\] val

---

### _partition_digest

```pony
fun box _partition_digest(
  state_routers: HashMap[String val, PartitionRouter val, HashEq[String val] val] ref,
  stateless_routers: HashMap[U128 val, StatelessPartitionRouter val, HashEq[U128 val] val] ref)
: HashMap[String val, HashMap[String val, HashMap[String val, Array[String val] val, HashEq[String val] val] val, HashEq[String val] val] val, HashEq[String val] val] ref
```
#### Parameters

*   state_routers: [HashMap](collections-HashMap)\[[String](builtin-String) val, [PartitionRouter](wallaroo-core-topology-PartitionRouter) val, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] ref
*   stateless_routers: [HashMap](collections-HashMap)\[[U128](builtin-U128) val, [StatelessPartitionRouter](wallaroo-core-topology-StatelessPartitionRouter) val, [HashEq](collections-HashEq)\[[U128](builtin-U128) val\] val\] ref

#### Returns

* [HashMap](collections-HashMap)\[[String](builtin-String) val, [HashMap](collections-HashMap)\[[String](builtin-String) val, [HashMap](collections-HashMap)\[[String](builtin-String) val, [Array](builtin-Array)\[[String](builtin-String) val\] val, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] ref

---

