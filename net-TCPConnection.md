# TCPConnection

A TCP connection. When connecting, the Happy Eyeballs algorithm is used.

The following code creates a client that connects to port 8989 of
the local host, writes "hello world", and listens for a response,
which it then prints.

```pony
use "net"

class MyTCPConnectionNotify is TCPConnectionNotify
  let _out: OutStream

  new create(out: OutStream) =>
    _out = out

  fun ref connected(conn: TCPConnection ref) =>
    conn.write("hello world")

  fun ref received(
    conn: TCPConnection ref,
    data: Array[U8] iso,
    times: USize)
    : Bool
  =>
    _out.print("GOT:" + String.from_array(consume data))
    conn.close()
    true

  fun ref connect_failed(conn: TCPConnection ref) =>
    None

actor Main
  new create(env: Env) =>
    try
      TCPConnection(env.root as AmbientAuth,
        recover MyTCPConnectionNotify(env.out) end, "", "8989")
    end
```

Note: when writing to the connection data will be silently discarded if the
connection has not yet been established.

## Backpressure support

### Write

The TCP protocol has built-in backpressure support. This is generally
experienced as the outgoing write buffer becoming full and being unable
to write all requested data to the socket. In `TCPConnection`, this is
hidden from the programmer. When this occurs, `TCPConnection` will buffer
the extra data until such time as it is able to be sent. Left unchecked,
this could result in uncontrolled queuing. To address this,
`TCPConnectionNotify` implements two methods `throttled` and `unthrottled`
that are called when backpressure is applied and released.

Upon receiving a `throttled` notification, your application has two choices
on how to handle it. One is to inform the Pony runtime that it can no
longer make progress and that runtime backpressure should be applied to
any actors sending this one messages. For example, you might construct your
application like:

```pony
// Here we have a TCPConnectionNotify that upon construction
// is given a BackpressureAuth token. This allows the notifier
// to inform the Pony runtime when to apply and release backpressure
// as the connection experiences it.
// Note the calls to
//
// Backpressure.apply(_auth)
// Backpressure.release(_auth)
//
// that apply and release backpressure as needed

use "backpressure"
use "collections"
use "net"

class SlowDown is TCPConnectionNotify
  let _auth: BackpressureAuth
  let _out: StdStream

  new iso create(auth: BackpressureAuth, out: StdStream) =>
    _auth = auth
    _out = out

  fun ref throttled(connection: TCPConnection ref) =>
    _out.print("Experiencing backpressure!")
    Backpressure.apply(_auth)

  fun ref unthrottled(connection: TCPConnection ref) =>
    _out.print("Releasing backpressure!")
    Backpressure.release(_auth)

  fun ref connect_failed(conn: TCPConnection ref) =>
    None

actor Main
  new create(env: Env) =>
    try
      let auth = env.root as AmbientAuth
      let socket = TCPConnection(auth, recover SlowDown(auth, env.out) end,
        "", "7669")
    end

```

Or if you want, you could handle backpressure by shedding load, that is,
dropping the extra data rather than carrying out the send. This might look
like:

```pony
use "net"

class ThrowItAway is TCPConnectionNotify
  var _throttled: Bool = false

  fun ref sent(conn: TCPConnection ref, data: ByteSeq): ByteSeq =>
    if not _throttled then
      data
    else
      ""
    end

  fun ref sentv(conn: TCPConnection ref, data: ByteSeqIter): ByteSeqIter =>
    if not _throttled then
      data
    else
      recover Array[String] end
    end

  fun ref throttled(connection: TCPConnection ref) =>
    _throttled = true

  fun ref unthrottled(connection: TCPConnection ref) =>
    _throttled = false

  fun ref connect_failed(conn: TCPConnection ref) =>
    None

actor Main
  new create(env: Env) =>
    try
      TCPConnection(env.root as AmbientAuth,
        recover ThrowItAway end, "", "7669")
    end
```

In general, unless you have a very specific use case, we strongly advise that
you don't implement a load shedding scheme where you drop data.

### Read

If your application is unable to keep up with data being sent to it over
a `TCPConnection` you can use the builtin read backpressure support to
pause reading the socket which will in turn start to exert backpressure on
the corresponding writer on the other end of that socket.

The `mute` behavior allow any other actors in your application to request
the cessation of additional reads until such time as `unmute` is called.
Please note that this cessation is not guaranteed to happen immediately as
it is the result of an asynchronous behavior call and as such will have to
wait for existing messages in the `TCPConnection`'s mailbox to be handled.

On non-windows platforms, your `TCPConnection` will not notice if the
other end of the connection closes until you unmute it. Unix type systems
like FreeBSD, Linux and OSX learn about a closed connection upon read. On
these platforms, you **must** call `unmute` on a muted connection to have
it close. Without calling `unmute` the `TCPConnection` actor will never
exit.


```pony
actor tag TCPConnection
```

## Constructors

### create

```pony
new tag create(
  auth: (AmbientAuth val | NetAuth val | TCPAuth val | 
    TCPConnectAuth val),
  notify: TCPConnectionNotify iso,
  host: String val,
  service: String val,
  from: String val = seq,
  init_size: USize val = seq,
  max_size: USize val = seq)
: TCPConnection tag^
```
#### Parameters

*   auth: ([AmbientAuth](builtin-AmbientAuth) val | [NetAuth](net-NetAuth) val | [TCPAuth](net-TCPAuth) val | 
    [TCPConnectAuth](net-TCPConnectAuth) val)
*   notify: [TCPConnectionNotify](net-TCPConnectionNotify) iso
*   host: [String](builtin-String) val
*   service: [String](builtin-String) val
*   from: [String](builtin-String) val = seq
*   init_size: [USize](builtin-USize) val = seq
*   max_size: [USize](builtin-USize) val = seq

#### Returns

* [TCPConnection](net-TCPConnection) tag^

---

### ip4

```pony
new tag ip4(
  auth: (AmbientAuth val | NetAuth val | TCPAuth val | 
    TCPConnectAuth val),
  notify: TCPConnectionNotify iso,
  host: String val,
  service: String val,
  from: String val = seq,
  init_size: USize val = seq,
  max_size: USize val = seq)
: TCPConnection tag^
```
#### Parameters

*   auth: ([AmbientAuth](builtin-AmbientAuth) val | [NetAuth](net-NetAuth) val | [TCPAuth](net-TCPAuth) val | 
    [TCPConnectAuth](net-TCPConnectAuth) val)
*   notify: [TCPConnectionNotify](net-TCPConnectionNotify) iso
*   host: [String](builtin-String) val
*   service: [String](builtin-String) val
*   from: [String](builtin-String) val = seq
*   init_size: [USize](builtin-USize) val = seq
*   max_size: [USize](builtin-USize) val = seq

#### Returns

* [TCPConnection](net-TCPConnection) tag^

---

### ip6

```pony
new tag ip6(
  auth: (AmbientAuth val | NetAuth val | TCPAuth val | 
    TCPConnectAuth val),
  notify: TCPConnectionNotify iso,
  host: String val,
  service: String val,
  from: String val = seq,
  init_size: USize val = seq,
  max_size: USize val = seq)
: TCPConnection tag^
```
#### Parameters

*   auth: ([AmbientAuth](builtin-AmbientAuth) val | [NetAuth](net-NetAuth) val | [TCPAuth](net-TCPAuth) val | 
    [TCPConnectAuth](net-TCPConnectAuth) val)
*   notify: [TCPConnectionNotify](net-TCPConnectionNotify) iso
*   host: [String](builtin-String) val
*   service: [String](builtin-String) val
*   from: [String](builtin-String) val = seq
*   init_size: [USize](builtin-USize) val = seq
*   max_size: [USize](builtin-USize) val = seq

#### Returns

* [TCPConnection](net-TCPConnection) tag^

---

### _accept

```pony
new tag _accept(
  listen: TCPListener tag,
  notify: TCPConnectionNotify iso,
  fd: U32 val,
  init_size: USize val = seq,
  max_size: USize val = seq)
: TCPConnection tag^
```
#### Parameters

*   listen: [TCPListener](net-TCPListener) tag
*   notify: [TCPConnectionNotify](net-TCPConnectionNotify) iso
*   fd: [U32](builtin-U32) val
*   init_size: [USize](builtin-USize) val = seq
*   max_size: [USize](builtin-USize) val = seq

#### Returns

* [TCPConnection](net-TCPConnection) tag^

---

## Public Behaviours

### write

Write a single sequence of bytes. Data will be silently discarded if the
connection has not yet been established though.


```pony
be write(
  data: (String val | Array[U8 val] val))
```
#### Parameters

*   data: ([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)

---

### writev

Write a sequence of sequences of bytes. Data will be silently discarded if
the connection has not yet been established though.


```pony
be writev(
  data: ByteSeqIter val)
```
#### Parameters

*   data: [ByteSeqIter](builtin-ByteSeqIter) val

---

### mute

Temporarily suspend reading off this TCPConnection until such time as
`unmute` is called.


```pony
be mute()
```

---

### unmute

Start reading off this TCPConnection again after having been muted.


```pony
be unmute()
```

---

### set_notify

Change the notifier.


```pony
be set_notify(
  notify: TCPConnectionNotify iso)
```
#### Parameters

*   notify: [TCPConnectionNotify](net-TCPConnectionNotify) iso

---

### dispose

Close the connection gracefully once all writes are sent.


```pony
be dispose()
```

---

## Public Functions

### local_address

Return the local IP address.


```pony
fun box local_address()
: NetAddress val
```

#### Returns

* [NetAddress](net-NetAddress) val

---

### remote_address

Return the remote IP address.


```pony
fun box remote_address()
: NetAddress val
```

#### Returns

* [NetAddress](net-NetAddress) val

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

### set_keepalive

Sets the TCP keepalive timeout to approximately `secs` seconds. Exact
timing is OS dependent. If `secs` is zero, TCP keepalive is disabled. TCP
keepalive is disabled by default. This can only be set on a connected
socket.


```pony
fun ref set_keepalive(
  secs: U32 val)
: None val
```
#### Parameters

*   secs: [U32](builtin-U32) val

#### Returns

* [None](builtin-None) val

---

### write_final

Write as much as possible to the socket. Set `_writeable` to `false` if not
everything was written. On an error, close the connection. This is for data
that has already been transformed by the notifier. Data will be silently
discarded if the connection has not yet been established though.


```pony
fun ref write_final(
  data: (String val | Array[U8 val] val))
: None val
```
#### Parameters

*   data: ([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)

#### Returns

* [None](builtin-None) val

---

### close

Attempt to perform a graceful shutdown. Don't accept new writes. If the
connection isn't muted then we won't finish closing until we get a zero
length read. If the connection is muted, perform a hard close and shut
down immediately.


```pony
fun ref close()
: None val
```

#### Returns

* [None](builtin-None) val

---

## Private Behaviours

### _event_notify

Handle socket events.


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

### _complete_writes

The OS has informed us that `len` bytes of pending writes have completed.
This occurs only with IOCP on Windows.


```pony
fun ref _complete_writes(
  len: U32 val)
: None val
```
#### Parameters

*   len: [U32](builtin-U32) val

#### Returns

* [None](builtin-None) val

---

### _pending_writes

Send pending data. If any data can't be sent, keep it and mark as not
writeable. On an error, dispose of the connection. Returns whether
it sent all pending data or not.


```pony
fun ref _pending_writes()
: Bool val
```

#### Returns

* [Bool](builtin-Bool) val

---

### _manage_pending_buffer

Manage pending buffer for data sent. Returns a boolean of whether
the pending buffer is empty or not.


```pony
fun ref _manage_pending_buffer(
  bytes_sent: USize val,
  bytes_to_send: USize val,
  num_to_send: USize val)
: Bool val ?
```
#### Parameters

*   bytes_sent: [USize](builtin-USize) val
*   bytes_to_send: [USize](builtin-USize) val
*   num_to_send: [USize](builtin-USize) val

#### Returns

* [Bool](builtin-Bool) val ?

---

### _complete_reads

The OS has informed us that `len` bytes of pending reads have completed.
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

### _read_buf_size

Resize the read buffer.


```pony
fun ref _read_buf_size()
: None val
```

#### Returns

* [None](builtin-None) val

---

### _queue_read

Begin an IOCP read on Windows.


```pony
fun ref _queue_read()
: None val
```

#### Returns

* [None](builtin-None) val

---

### _pending_reads

Unless this connection is currently muted, read while data is available,
guessing the next packet length as we go. If we read 4 kb of data, send
ourself a resume message and stop reading, to avoid starving other actors.


```pony
fun ref _pending_reads()
: None val
```

#### Returns

* [None](builtin-None) val

---

### _notify_connecting

Inform the notifier that we're connecting.


```pony
fun ref _notify_connecting()
: None val
```

#### Returns

* [None](builtin-None) val

---

### _close

```pony
fun ref _close()
: None val
```

#### Returns

* [None](builtin-None) val

---

### _try_shutdown

If we have closed and we have no remaining writes or pending connections,
then shutdown.


```pony
fun ref _try_shutdown()
: None val
```

#### Returns

* [None](builtin-None) val

---

### _hard_close

When an error happens, do a non-graceful close.


```pony
fun ref _hard_close()
: None val
```

#### Returns

* [None](builtin-None) val

---

### _apply_backpressure

```pony
fun ref _apply_backpressure()
: None val
```

#### Returns

* [None](builtin-None) val

---

### _release_backpressure

```pony
fun ref _release_backpressure()
: None val
```

#### Returns

* [None](builtin-None) val

---

