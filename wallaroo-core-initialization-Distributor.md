# Distributor

```pony
trait tag Distributor
```

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

