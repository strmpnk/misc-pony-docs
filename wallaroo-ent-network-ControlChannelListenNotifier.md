# ControlChannelListenNotifier

```pony
class ref ControlChannelListenNotifier is
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
  is_initializer: Bool val,
  initializer: (ClusterInitializer tag | None val) = seq,
  layout_initializer: LayoutInitializer tag,
  recovery: Recovery tag,
  recovery_replayer: RecoveryReplayer tag,
  router_registry: RouterRegistry tag,
  recovery_file: FilePath val,
  data_host: String val,
  data_service: String val,
  event_log: EventLog tag,
  recovery_file_cleaner: RecoveryFileCleaner tag)
: ControlChannelListenNotifier iso^
```
#### Parameters

*   name: [String](builtin-String) val
*   auth: [AmbientAuth](builtin-AmbientAuth) val
*   connections: [Connections](wallaroo-ent-network-Connections) tag
*   is_initializer: [Bool](builtin-Bool) val
*   initializer: ([ClusterInitializer](wallaroo-core-initialization-ClusterInitializer) tag | [None](builtin-None) val) = seq
*   layout_initializer: [LayoutInitializer](wallaroo-core-initialization-LayoutInitializer) tag
*   recovery: [Recovery](wallaroo-ent-recovery-Recovery) tag
*   recovery_replayer: [RecoveryReplayer](wallaroo-ent-recovery-RecoveryReplayer) tag
*   router_registry: [RouterRegistry](wallaroo-ent-router_registry-RouterRegistry) tag
*   recovery_file: [FilePath](files-FilePath) val
*   data_host: [String](builtin-String) val
*   data_service: [String](builtin-String) val
*   event_log: [EventLog](wallaroo-ent-recovery-EventLog) tag
*   recovery_file_cleaner: [RecoveryFileCleaner](wallaroo-core-common-RecoveryFileCleaner) tag

#### Returns

* [ControlChannelListenNotifier](wallaroo-ent-network-ControlChannelListenNotifier) iso^

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

