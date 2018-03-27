# LayoutInitializer

```pony
trait tag LayoutInitializer
```

## Public Behaviours

### initialize

```pony
be initialize(
  cluster_initializer: (ClusterInitializer tag | None val) = seq,
  recovering: Bool val)
```
#### Parameters

*   cluster_initializer: ([ClusterInitializer](wallaroo-core-initialization-ClusterInitializer) tag | [None](builtin-None) val) = seq
*   recovering: [Bool](builtin-Bool) val

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

### receive_immigrant_step

```pony
be receive_immigrant_step(
  msg: StepMigrationMsg val)
```
#### Parameters

*   msg: [StepMigrationMsg](wallaroo-core-messages-StepMigrationMsg) val

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

