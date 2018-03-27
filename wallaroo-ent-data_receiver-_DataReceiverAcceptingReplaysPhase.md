# _DataReceiverAcceptingReplaysPhase

```pony
class ref _DataReceiverAcceptingReplaysPhase is
  _DataReceiverProcessingPhase ref
```

#### Implements

* [_DataReceiverProcessingPhase](wallaroo-ent-data_receiver-_DataReceiverProcessingPhase) ref

---

## Constructors

### create

```pony
new ref create(
  dr: DataReceiver ref)
: _DataReceiverAcceptingReplaysPhase ref^
```
#### Parameters

*   dr: [DataReceiver](wallaroo-ent-data_receiver-DataReceiver) ref

#### Returns

* [_DataReceiverAcceptingReplaysPhase](wallaroo-ent-data_receiver-_DataReceiverAcceptingReplaysPhase) ref^

---

## Public Functions

### data_connect

```pony
fun box data_connect()
: None val
```

#### Returns

* [None](builtin-None) val

---

