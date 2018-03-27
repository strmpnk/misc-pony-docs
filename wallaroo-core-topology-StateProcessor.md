# StateProcessor\[S: [State](wallaroo-core-state-State) ref\]

```pony
trait val StateProcessor[S: State ref] is
  BasicComputation ref
```

#### Implements

* [BasicComputation](wallaroo-core-topology-BasicComputation) ref

---

## Public Functions

### name

```pony
fun box name()
: String val
```

#### Returns

* [String](builtin-String) val

---

### apply

```pony
fun box apply(
  state: S,
  sc_repo: StateChangeRepository[S] ref,
  omni_router: OmniRouter val,
  metric_name: String val,
  pipeline_time_spent: U64 val,
  producer: Producer ref,
  i_msg_uid: U128 val,
  frac_ids: (Array[U32 val] val | None val),
  latest_ts: U64 val,
  metrics_id: U16 val,
  worker_ingress_ts: U64 val)
: (Bool val , (StateChange[S] ref | DirectStateChange val | None val) , U64 val , 
    U64 val , U64 val)
```
#### Parameters

*   state: S
*   sc_repo: [StateChangeRepository](wallaroo-core-state-StateChangeRepository)\[S\] ref
*   omni_router: [OmniRouter](wallaroo-core-topology-OmniRouter) val
*   metric_name: [String](builtin-String) val
*   pipeline_time_spent: [U64](builtin-U64) val
*   producer: [Producer](wallaroo-core-common-Producer) ref
*   i_msg_uid: [U128](builtin-U128) val
*   frac_ids: ([Array](builtin-Array)\[[U32](builtin-U32) val\] val | [None](builtin-None) val)
*   latest_ts: [U64](builtin-U64) val
*   metrics_id: [U16](builtin-U16) val
*   worker_ingress_ts: [U64](builtin-U64) val

#### Returns

* ([Bool](builtin-Bool) val , ([StateChange](wallaroo-core-state-StateChange)\[S\] ref | [DirectStateChange](wallaroo-core-state-DirectStateChange) val | [None](builtin-None) val) , [U64](builtin-U64) val , 
    [U64](builtin-U64) val , [U64](builtin-U64) val)

---

