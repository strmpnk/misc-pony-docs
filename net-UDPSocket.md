# UDPSocket

Creates a UDP socket that can be used for sending and receiving UDP messages.

The following examples create:
* an echo server that listens for connections and returns whatever message it
  receives
* a client that connects to the server, sends a message, and prints the
  message it receives in response

The server is implemented like this:

```pony
use "net"

class MyUDPNotify is UDPNotify
  fun ref received(
    sock: UDPSocket ref,
    data: Array[U8] iso,
    from: NetAddress)
  =>
    sock.write(consume data, from)

  fun ref not_listening(sock: UDPSocket ref) =>
    None

actor Main
  new create(env: Env) =>
    try
      UDPSocket(env.root as AmbientAuth,
        MyUDPNotify, "", "8989")
    end
```

The client is implemented like this:

```pony
use "net"

class MyUDPNotify is UDPNotify
  let _out: OutStream
  let _destination: NetAddress

  new create(
    out: OutStream,
    destination: NetAddress)
  =>
    _out = out
    _destination = destination

  fun ref listening(sock: UDPSocket ref) =>
    sock.write("hello world", _destination)

  fun ref received(
    sock: UDPSocket ref,
    data: Array[U8] iso,
    from: NetAddress)
  =>
    _out.print("GOT:" + String.from_array(consume data))
    sock.dispose()

  fun ref not_listening(sock: UDPSocket ref) =>
    None

actor Main
  new create(env: Env) =>
    try
      let destination =
        DNS.ip4(env.root as AmbientAuth, "localhost", "8989")(0)?
      UDPSocket(env.root as AmbientAuth,
        recover MyUDPNotify(env.out, consume destination) end)
    end
```


```pony
actor tag UDPSocket
```

## Constructors

### create

```pony
new tag create(
  auth: (AmbientAuth val | NetAuth val | UDPAuth val),
  notify: UDPNotify iso,
  host: String val = seq,
  service: String val = seq,
  size: USize val = seq)
: UDPSocket tag^
```
#### Parameters

*   auth: ([AmbientAuth](builtin-AmbientAuth) val | [NetAuth](net-NetAuth) val | [UDPAuth](net-UDPAuth) val)
*   notify: [UDPNotify](net-UDPNotify) iso
*   host: [String](builtin-String) val = seq
*   service: [String](builtin-String) val = seq
*   size: [USize](builtin-USize) val = seq

#### Returns

* [UDPSocket](net-UDPSocket) tag^

---

### ip4

```pony
new tag ip4(
  auth: (AmbientAuth val | NetAuth val | UDPAuth val),
  notify: UDPNotify iso,
  host: String val = seq,
  service: String val = seq,
  size: USize val = seq)
: UDPSocket tag^
```
#### Parameters

*   auth: ([AmbientAuth](builtin-AmbientAuth) val | [NetAuth](net-NetAuth) val | [UDPAuth](net-UDPAuth) val)
*   notify: [UDPNotify](net-UDPNotify) iso
*   host: [String](builtin-String) val = seq
*   service: [String](builtin-String) val = seq
*   size: [USize](builtin-USize) val = seq

#### Returns

* [UDPSocket](net-UDPSocket) tag^

---

### ip6

```pony
new tag ip6(
  auth: (AmbientAuth val | NetAuth val | UDPAuth val),
  notify: UDPNotify iso,
  host: String val = seq,
  service: String val = seq,
  size: USize val = seq)
: UDPSocket tag^
```
#### Parameters

*   auth: ([AmbientAuth](builtin-AmbientAuth) val | [NetAuth](net-NetAuth) val | [UDPAuth](net-UDPAuth) val)
*   notify: [UDPNotify](net-UDPNotify) iso
*   host: [String](builtin-String) val = seq
*   service: [String](builtin-String) val = seq
*   size: [USize](builtin-USize) val = seq

#### Returns

* [UDPSocket](net-UDPSocket) tag^

---

## Public Behaviours

### write

Write a single sequence of bytes.


```pony
be write(
  data: (String val | Array[U8 val] val),
  to: NetAddress val)
```
#### Parameters

*   data: ([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)
*   to: [NetAddress](net-NetAddress) val

---

### writev

Write a sequence of sequences of bytes.


```pony
be writev(
  data: ByteSeqIter val,
  to: NetAddress val)
```
#### Parameters

*   data: [ByteSeqIter](builtin-ByteSeqIter) val
*   to: [NetAddress](net-NetAddress) val

---

### set_notify

Change the notifier.


```pony
be set_notify(
  notify: UDPNotify iso)
```
#### Parameters

*   notify: [UDPNotify](net-UDPNotify) iso

---

### set_broadcast

Enable or disable broadcasting from this socket.


```pony
be set_broadcast(
  state: Bool val)
```
#### Parameters

*   state: [Bool](builtin-Bool) val

---

### set_multicast_interface

By default, the OS will choose which address is used to send packets bound
for multicast addresses. This can be used to force a specific interface. To
revert to allowing the OS to choose, call with an empty string.


```pony
be set_multicast_interface(
  from: String val = seq)
```
#### Parameters

*   from: [String](builtin-String) val = seq

---

### set_multicast_loopback

By default, packets sent to a multicast address will be received by the
sending system if it has subscribed to that address. Disabling loopback
prevents this.


```pony
be set_multicast_loopback(
  loopback: Bool val)
```
#### Parameters

*   loopback: [Bool](builtin-Bool) val

---

### set_multicast_ttl

Set the TTL for multicast sends. Defaults to 1.


```pony
be set_multicast_ttl(
  ttl: U8 val)
```
#### Parameters

*   ttl: [U8](builtin-U8) val

---

### multicast_join

Add a multicast group. This can be limited to packets arriving on a
specific interface.


```pony
be multicast_join(
  group: String val,
  to: String val = seq)
```
#### Parameters

*   group: [String](builtin-String) val
*   to: [String](builtin-String) val = seq

---

### multicast_leave

Drop a multicast group. This can be limited to packets arriving on a
specific interface. No attempt is made to check that this socket has
previously added this group.


```pony
be multicast_leave(
  group: String val,
  to: String val = seq)
```
#### Parameters

*   group: [String](builtin-String) val
*   to: [String](builtin-String) val = seq

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

### _read_again

Resume reading.


```pony
be _read_again()
```

---

## Private Functions

### _pending_reads

Read while data is available, guessing the next packet length as we go. If
we read 4 kb of data, send ourself a resume message and stop reading, to
avoid starving other actors.


```pony
fun ref _pending_reads()
: None val
```

#### Returns

* [None](builtin-None) val

---

### _complete_reads

The OS has informed as that len bytes of pending reads have completed.
This occurs only with IOCP on Windows.


```pony
fun ref _complete_reads(
  len: U32 val)
: None val
```
#### Parameters

*   len: [U32](builtin-U32) val

#### Returns

* [None](builtin-None) val

---

### _start_next_read

Start our next receive.
This is used only with IOCP on Windows.


```pony
fun ref _start_next_read()
: None val
```

#### Returns

* [None](builtin-None) val

---

### _write

Write the datagram to the socket.


```pony
fun ref _write(
  data: (String val | Array[U8 val] val),
  to: NetAddress val)
: None val
```
#### Parameters

*   data: ([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)
*   to: [NetAddress](net-NetAddress) val

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

### _close

Inform the notifier that we've closed.


```pony
fun ref _close()
: None val
```

#### Returns

* [None](builtin-None) val

---

