# DataChannelListener

```pony
actor tag DataChannelListener
```

## Constructors

### create

```pony
new tag create(
  auth: (AmbientAuth val | NetAuth val | TCPAuth val | 
    TCPListenAuth val),
  notify: DataChannelListenNotify iso,
  router_registry: RouterRegistry tag,
  host: String val = seq,
  service: String val = seq,
  limit: USize val = seq,
  init_size: USize val = seq,
  max_size: USize val = seq)
: DataChannelListener tag^
```
#### Parameters

*   auth: ([AmbientAuth](builtin-AmbientAuth) val | [NetAuth](net-NetAuth) val | [TCPAuth](net-TCPAuth) val | 
    [TCPListenAuth](net-TCPListenAuth) val)
*   notify: [DataChannelListenNotify](wallaroo-core-data_channel-DataChannelListenNotify) iso
*   router_registry: [RouterRegistry](wallaroo-ent-router_registry-RouterRegistry) tag
*   host: [String](builtin-String) val = seq
*   service: [String](builtin-String) val = seq
*   limit: [USize](builtin-USize) val = seq
*   init_size: [USize](builtin-USize) val = seq
*   max_size: [USize](builtin-USize) val = seq

#### Returns

* [DataChannelListener](wallaroo-core-data_channel-DataChannelListener) tag^

---

## Public Behaviours

### set_notify

Change the notifier.


```pony
be set_notify(
  notify: DataChannelListenNotify iso)
```
#### Parameters

*   notify: [DataChannelListenNotify](wallaroo-core-data_channel-DataChannelListenNotify) iso

---

### dispose

Stop listening.


```pony
be dispose()
```

---

## Public Functions

### requested_address

Return the host and service that were originally provided to the
@pony_os_listen_tcp method.
Use this if `local_address().name()` fails.


```pony
fun box requested_address()
: (String val , String val)
```

#### Returns

* ([String](builtin-String) val , [String](builtin-String) val)

---

### local_address

Return the bound IP address.


```pony
fun box local_address()
: NetAddress val
```

#### Returns

* [NetAddress](net-NetAddress) val

---

### close

Dispose of resources.


```pony
fun ref close()
: None val
```

#### Returns

* [None](builtin-None) val

---

## Private Behaviours

### _event_notify

When we are readable, we accept new connections until none remain.


```pony
be _event_notify(
  event: Pointer[AsioEvent val] tag,
  flags: U32 val,
  arg: U32 val)
```
#### Parameters

*   event: [Pointer](builtin-Pointer)\[[AsioEvent](builtin-AsioEvent) val\] tag
*   flags: [U32](builtin-U32) val
*   arg: [U32](builtin-U32) val

---

### _conn_closed

An accepted connection has closed. If we have dropped below the limit, try
to accept new connections.


```pony
be _conn_closed()
```

---

## Private Functions

### _accept

Accept connections as long as we have spawned fewer than our limit.


```pony
fun ref _accept(
  ns: U32 val = seq)
: None val
```
#### Parameters

*   ns: [U32](builtin-U32) val = seq

#### Returns

* [None](builtin-None) val

---

### _spawn

Spawn a new connection.


```pony
fun ref _spawn(
  ns: U32 val)
: None val
```
#### Parameters

*   ns: [U32](builtin-U32) val

#### Returns

* [None](builtin-None) val

---

### _notify_listening

Inform the notifier that we're listening.


```pony
fun ref _notify_listening()
: None val
```

#### Returns

* [None](builtin-None) val

---

