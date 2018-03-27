# DataChannelListenNotifier

```pony
class ref DataChannelListenNotifier is
  DataChannelListenNotify ref
```

#### Implements

* [DataChannelListenNotify](wallaroo-core-data_channel-DataChannelListenNotify) ref

---

## Constructors

### create

```pony
new iso create(
  name: String val,
  auth: AmbientAuth val,
  connections: Connections tag,
  is_initializer: Bool val,
  metrics_reporter: MetricsReporter iso,
  recovery_file: FilePath val,
  layout_initializer: LayoutInitializer tag,
  data_receivers: DataReceivers tag,
  recovery_replayer: RecoveryReplayer tag,
  router_registry: RouterRegistry tag,
  joining: Bool val = seq)
: DataChannelListenNotifier iso^
```
#### Parameters

*   name: [String](builtin-String) val
*   auth: [AmbientAuth](builtin-AmbientAuth) val
*   connections: [Connections](wallaroo-ent-network-Connections) tag
*   is_initializer: [Bool](builtin-Bool) val
*   metrics_reporter: [MetricsReporter](wallaroo-core-metrics-MetricsReporter) iso
*   recovery_file: [FilePath](files-FilePath) val
*   layout_initializer: [LayoutInitializer](wallaroo-core-initialization-LayoutInitializer) tag
*   data_receivers: [DataReceivers](wallaroo-ent-data_receiver-DataReceivers) tag
*   recovery_replayer: [RecoveryReplayer](wallaroo-ent-recovery-RecoveryReplayer) tag
*   router_registry: [RouterRegistry](wallaroo-ent-router_registry-RouterRegistry) tag
*   joining: [Bool](builtin-Bool) val = seq

#### Returns

* [DataChannelListenNotifier](wallaroo-core-data_channel-DataChannelListenNotifier) iso^

---

## Public Functions

### listening

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

### connected

```pony
fun ref connected(
  listen: DataChannelListener ref,
  router_registry: RouterRegistry tag)
: DataChannelNotify iso^
```
#### Parameters

*   listen: [DataChannelListener](wallaroo-core-data_channel-DataChannelListener) ref
*   router_registry: [RouterRegistry](wallaroo-ent-router_registry-RouterRegistry) tag

#### Returns

* [DataChannelNotify](wallaroo-core-data_channel-DataChannelNotify) iso^

---

### closed

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

