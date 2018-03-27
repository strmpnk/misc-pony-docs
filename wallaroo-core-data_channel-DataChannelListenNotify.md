# DataChannelListenNotify

Notifications for DataChannel listeners.

For an example of using this class, please see the documentation for the
`DataChannelListener` actor.


```pony
interface ref DataChannelListenNotify
```

## Public Functions

### listening

Called when the listener has been bound to an address.


```pony
fun ref listening(
  listen: DataChannelListener ref)
: None val
```
#### Parameters

*   listen: [DataChannelListener](wallaroo-core-data_channel-DataChannelListener) ref

#### Returns

* [None](builtin-None) val

---

### not_listening

Called if it wasn't possible to bind the listener to an address.


```pony
fun ref not_listening(
  listen: DataChannelListener ref)
: None val
```
#### Parameters

*   listen: [DataChannelListener](wallaroo-core-data_channel-DataChannelListener) ref

#### Returns

* [None](builtin-None) val

---

### closed

Called when the listener is closed.


```pony
fun ref closed(
  listen: DataChannelListener ref)
: None val
```
#### Parameters

*   listen: [DataChannelListener](wallaroo-core-data_channel-DataChannelListener) ref

#### Returns

* [None](builtin-None) val

---

### connected

Create a new DataChannelNotify to attach to a new DataChannel for a
newly established connection to the server.


```pony
fun ref connected(
  listen: DataChannelListener ref,
  router_registry: RouterRegistry tag)
: DataChannelNotify iso^ ?
```
#### Parameters

*   listen: [DataChannelListener](wallaroo-core-data_channel-DataChannelListener) ref
*   router_registry: [RouterRegistry](wallaroo-ent-router_registry-RouterRegistry) tag

#### Returns

* [DataChannelNotify](wallaroo-core-data_channel-DataChannelNotify) iso^ ?

---

