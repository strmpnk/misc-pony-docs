# ExternalChannelListenNotifier

```pony
class ref ExternalChannelListenNotifier is
  TCPListenNotify ref
```

#### Implements

* [TCPListenNotify](net-TCPListenNotify) ref

---

## Constructors

### create

```pony
new iso create(
  name: String val,
  auth: AmbientAuth val,
  connections: Connections tag,
  recovery_file_cleaner: RecoveryFileCleaner tag,
  local_topology_initializer: LocalTopologyInitializer tag)
: ExternalChannelListenNotifier iso^
```
#### Parameters

*   name: [String](builtin-String) val
*   auth: [AmbientAuth](builtin-AmbientAuth) val
*   connections: [Connections](wallaroo-ent-network-Connections) tag
*   recovery_file_cleaner: [RecoveryFileCleaner](wallaroo-core-common-RecoveryFileCleaner) tag
*   local_topology_initializer: [LocalTopologyInitializer](wallaroo-core-initialization-LocalTopologyInitializer) tag

#### Returns

* [ExternalChannelListenNotifier](wallaroo-ent-network-ExternalChannelListenNotifier) iso^

---

## Public Functions

### listening

```pony
fun ref listening(
  listen: TCPListener ref)
: None val
```
#### Parameters

*   listen: [TCPListener](net-TCPListener) ref

#### Returns

* [None](builtin-None) val

---

### not_listening

```pony
fun ref not_listening(
  listen: TCPListener ref)
: None val
```
#### Parameters

*   listen: [TCPListener](net-TCPListener) ref

#### Returns

* [None](builtin-None) val

---

### connected

```pony
fun ref connected(
  listen: TCPListener ref)
: TCPConnectionNotify iso^
```
#### Parameters

*   listen: [TCPListener](net-TCPListener) ref

#### Returns

* [TCPConnectionNotify](net-TCPConnectionNotify) iso^

---

### closed

```pony
fun ref closed(
  listen: TCPListener ref)
: None val
```
#### Parameters

*   listen: [TCPListener](net-TCPListener) ref

#### Returns

* [None](builtin-None) val

---

