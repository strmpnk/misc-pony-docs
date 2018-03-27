# SpikeWrapper

```pony
primitive val SpikeWrapper
```

## Constructors

### create

```pony
new val create()
: SpikeWrapper val^
```

#### Returns

* [SpikeWrapper](wallaroo-ent-spike-SpikeWrapper) val^

---

## Public Functions

### apply

```pony
fun box apply(
  letter: WallarooOutgoingNetworkActorNotify iso,
  config: SpikeConfig val)
: WallarooOutgoingNetworkActorNotify iso^
```
#### Parameters

*   letter: [WallarooOutgoingNetworkActorNotify](wallaroo-ent-network-WallarooOutgoingNetworkActorNotify) iso
*   config: [SpikeConfig](wallaroo-ent-spike-SpikeConfig) val

#### Returns

* [WallarooOutgoingNetworkActorNotify](wallaroo-ent-network-WallarooOutgoingNetworkActorNotify) iso^

---

### eq

```pony
fun box eq(
  that: SpikeWrapper val)
: Bool val
```
#### Parameters

*   that: [SpikeWrapper](wallaroo-ent-spike-SpikeWrapper) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: SpikeWrapper val)
: Bool val
```
#### Parameters

*   that: [SpikeWrapper](wallaroo-ent-spike-SpikeWrapper) val

#### Returns

* [Bool](builtin-Bool) val

---

