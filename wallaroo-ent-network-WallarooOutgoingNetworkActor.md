# WallarooOutgoingNetworkActor

```pony
interface ref WallarooOutgoingNetworkActor
```

## Public Functions

### set_nodelay

Turn Nagle on/off. Defaults to on. This can only be set on a connected
socket.


```pony
fun ref set_nodelay(
  state: Bool val)
: None val
```
#### Parameters

*   state: [Bool](builtin-Bool) val

#### Returns

* [None](builtin-None) val

---

### expect

A `received` call on the notifier must contain exactly `qty` bytes. If
`qty` is zero, the call can contain any amount of data. This has no effect
if called in the `sent` notifier callback.


```pony
fun ref expect(
  qty: USize val = seq)
: None val
```
#### Parameters

*   qty: [USize](builtin-USize) val = seq

#### Returns

* [None](builtin-None) val

---

### receive_connect_ack

Called when processing an acknowledgment of successful connection to a
DataReceiver


```pony
fun ref receive_connect_ack(
  seq_id: U64 val)
: None val
```
#### Parameters

*   seq_id: [U64](builtin-U64) val

#### Returns

* [None](builtin-None) val

---

### start_normal_sending

Called when we are ready to begin sending messages normally (after
replay is complete)


```pony
fun ref start_normal_sending()
: None val
```

#### Returns

* [None](builtin-None) val

---

### receive_ack

Called when processing an acknowledgment of a message sent over the
connection


```pony
fun ref receive_ack(
  seq_id: U64 val)
: None val
```
#### Parameters

*   seq_id: [U64](builtin-U64) val

#### Returns

* [None](builtin-None) val

---

### close

Called to close the connection in a graceful fashion


```pony
fun ref close()
: None val
```

#### Returns

* [None](builtin-None) val

---

