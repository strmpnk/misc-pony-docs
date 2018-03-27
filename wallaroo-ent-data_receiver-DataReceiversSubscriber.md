# DataReceiversSubscriber

```pony
interface ref DataReceiversSubscriber
```

## Public Behaviours

### data_receiver_added

```pony
be data_receiver_added(
  sender_name: String val,
  boundary_step_id: U128 val,
  dr: DataReceiver tag)
```
#### Parameters

*   sender_name: [String](builtin-String) val
*   boundary_step_id: [U128](builtin-U128) val
*   dr: [DataReceiver](wallaroo-ent-data_receiver-DataReceiver) tag

---

