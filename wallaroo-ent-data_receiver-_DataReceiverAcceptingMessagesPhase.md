# _DataReceiverAcceptingMessagesPhase

```pony
class ref _DataReceiverAcceptingMessagesPhase is
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
: _DataReceiverAcceptingMessagesPhase ref^
```
#### Parameters

*   dr: [DataReceiver](wallaroo-ent-data_receiver-DataReceiver) ref

#### Returns

* [_DataReceiverAcceptingMessagesPhase](wallaroo-ent-data_receiver-_DataReceiverAcceptingMessagesPhase) ref^

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

