# TCPListener

Listens for new network connections.

The following program creates an echo server that listens for
connections on port 8989 and echoes back any data it receives.

```pony
use "net"

class MyTCPConnectionNotify is TCPConnectionNotify
  fun ref received(
    conn: TCPConnection ref,
    data: Array[U8] iso,
    times: USize)
    : Bool
  =>
    conn.write(String.from_array(consume data))
    true

  fun ref connect_failed(conn: TCPConnection ref) =>
    None

class MyTCPListenNotify is TCPListenNotify
  fun ref connected(listen: TCPListener ref): TCPConnectionNotify iso^ =>
    MyTCPConnectionNotify

  fun ref not_listening(listen: TCPListener ref) =>
    None

actor Main
  new create(env: Env) =>
    try
      TCPListener(env.root as AmbientAuth,
        recover MyTCPListenNotify end, "", "8989")
    end
```


```pony
actor tag TCPListener
```

## Constructors

### create

```pony
new tag create(
  auth: (AmbientAuth val | NetAuth val | TCPAuth val | 
    TCPListenAuth val),
  notify: TCPListenNotify iso,
  host: String val = seq,
  service: String val = seq,
  limit: USize val = seq,
  init_size: USize val = seq,
  max_size: USize val = seq)
: TCPListener tag^
```
#### Parameters

*   auth: ([AmbientAuth](builtin-AmbientAuth) val | [NetAuth](net-NetAuth) val | [TCPAuth](net-TCPAuth) val | 
    [TCPListenAuth](net-TCPListenAuth) val)
*   notify: [TCPListenNotify](net-TCPListenNotify) iso
*   host: [String](builtin-String) val = seq
*   service: [String](builtin-String) val = seq
*   limit: [USize](builtin-USize) val = seq
*   init_size: [USize](builtin-USize) val = seq
*   max_size: [USize](builtin-USize) val = seq

#### Returns

* [TCPListener](net-TCPListener) tag^

---

### ip4

```pony
new tag ip4(
  auth: (AmbientAuth val | NetAuth val | TCPAuth val | 
    TCPListenAuth val),
  notify: TCPListenNotify iso,
  host: String val = seq,
  service: String val = seq,
  limit: USize val = seq,
  init_size: USize val = seq,
  max_size: USize val = seq)
: TCPListener tag^
```
#### Parameters

*   auth: ([AmbientAuth](builtin-AmbientAuth) val | [NetAuth](net-NetAuth) val | [TCPAuth](net-TCPAuth) val | 
    [TCPListenAuth](net-TCPListenAuth) val)
*   notify: [TCPListenNotify](net-TCPListenNotify) iso
*   host: [String](builtin-String) val = seq
*   service: [String](builtin-String) val = seq
*   limit: [USize](builtin-USize) val = seq
*   init_size: [USize](builtin-USize) val = seq
*   max_size: [USize](builtin-USize) val = seq

#### Returns

* [TCPListener](net-TCPListener) tag^

---

### ip6

```pony
new tag ip6(
  auth: (AmbientAuth val | NetAuth val | TCPAuth val | 
    TCPListenAuth val),
  notify: TCPListenNotify iso,
  host: String val = seq,
  service: String val = seq,
  limit: USize val = seq,
  init_size: USize val = seq,
  max_size: USize val = seq)
: TCPListener tag^
```
#### Parameters

*   auth: ([AmbientAuth](builtin-AmbientAuth) val | [NetAuth](net-NetAuth) val | [TCPAuth](net-TCPAuth) val | 
    [TCPListenAuth](net-TCPListenAuth) val)
*   notify: [TCPListenNotify](net-TCPListenNotify) iso
*   host: [String](builtin-String) val = seq
*   service: [String](builtin-String) val = seq
*   limit: [USize](builtin-USize) val = seq
*   init_size: [USize](builtin-USize) val = seq
*   max_size: [USize](builtin-USize) val = seq

#### Returns

* [TCPListener](net-TCPListener) tag^

---

## Public Behaviours

### set_notify

Change the notifier.


```pony
be set_notify(
  notify: TCPListenNotify iso)
```
#### Parameters

*   notify: [TCPListenNotify](net-TCPListenNotify) iso

---

### dispose

Stop listening.


```pony
be dispose()
```

---

## Public Functions

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

