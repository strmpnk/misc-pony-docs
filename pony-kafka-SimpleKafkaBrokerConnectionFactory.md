# SimpleKafkaBrokerConnectionFactory

```pony
class ref SimpleKafkaBrokerConnectionFactory is
  KafkaBrokerConnectionFactory ref
```

#### Implements

* [KafkaBrokerConnectionFactory](pony-kafka-KafkaBrokerConnectionFactory) ref

---

## Constructors

### create

```pony
new val create()
: SimpleKafkaBrokerConnectionFactory val^
```

#### Returns

* [SimpleKafkaBrokerConnectionFactory](pony-kafka-SimpleKafkaBrokerConnectionFactory) val^

---

## Public Functions

### apply

```pony
fun box apply(
  auth: (AmbientAuth val | NetAuth val | TCPAuth val | 
    TCPConnectAuth val),
  notify: CustomTCPConnectionNotify iso,
  host: String val,
  service: String val,
  from: String val = seq,
  init_size: USize val = seq,
  max_size: USize val = seq)
: KafkaBrokerConnection tag
```
#### Parameters

*   auth: ([AmbientAuth](builtin-AmbientAuth) val | [NetAuth](net-NetAuth) val | [TCPAuth](net-TCPAuth) val | 
    [TCPConnectAuth](net-TCPConnectAuth) val)
*   notify: [CustomTCPConnectionNotify](.-customnet-CustomTCPConnectionNotify) iso
*   host: [String](builtin-String) val
*   service: [String](builtin-String) val
*   from: [String](builtin-String) val = seq
*   init_size: [USize](builtin-USize) val = seq
*   max_size: [USize](builtin-USize) val = seq

#### Returns

* [KafkaBrokerConnection](pony-kafka-KafkaBrokerConnection) tag

---

### ip4

```pony
fun box ip4(
  auth: (AmbientAuth val | NetAuth val | TCPAuth val | 
    TCPConnectAuth val),
  notify: CustomTCPConnectionNotify iso,
  host: String val,
  service: String val,
  from: String val = seq,
  init_size: USize val = seq,
  max_size: USize val = seq)
: KafkaBrokerConnection tag
```
#### Parameters

*   auth: ([AmbientAuth](builtin-AmbientAuth) val | [NetAuth](net-NetAuth) val | [TCPAuth](net-TCPAuth) val | 
    [TCPConnectAuth](net-TCPConnectAuth) val)
*   notify: [CustomTCPConnectionNotify](.-customnet-CustomTCPConnectionNotify) iso
*   host: [String](builtin-String) val
*   service: [String](builtin-String) val
*   from: [String](builtin-String) val = seq
*   init_size: [USize](builtin-USize) val = seq
*   max_size: [USize](builtin-USize) val = seq

#### Returns

* [KafkaBrokerConnection](pony-kafka-KafkaBrokerConnection) tag

---

### ip6

```pony
fun box ip6(
  auth: (AmbientAuth val | NetAuth val | TCPAuth val | 
    TCPConnectAuth val),
  notify: CustomTCPConnectionNotify iso,
  host: String val,
  service: String val,
  from: String val = seq,
  init_size: USize val = seq,
  max_size: USize val = seq)
: KafkaBrokerConnection tag
```
#### Parameters

*   auth: ([AmbientAuth](builtin-AmbientAuth) val | [NetAuth](net-NetAuth) val | [TCPAuth](net-TCPAuth) val | 
    [TCPConnectAuth](net-TCPConnectAuth) val)
*   notify: [CustomTCPConnectionNotify](.-customnet-CustomTCPConnectionNotify) iso
*   host: [String](builtin-String) val
*   service: [String](builtin-String) val
*   from: [String](builtin-String) val = seq
*   init_size: [USize](builtin-USize) val = seq
*   max_size: [USize](builtin-USize) val = seq

#### Returns

* [KafkaBrokerConnection](pony-kafka-KafkaBrokerConnection) tag

---

