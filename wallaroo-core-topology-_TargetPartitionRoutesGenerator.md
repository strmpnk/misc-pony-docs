# _TargetPartitionRoutesGenerator

```pony
primitive val _TargetPartitionRoutesGenerator
```

## Constructors

### create

```pony
new val create()
: _TargetPartitionRoutesGenerator val^
```

#### Returns

* [_TargetPartitionRoutesGenerator](wallaroo-core-topology-_TargetPartitionRoutesGenerator) val^

---

## Public Functions

### apply

```pony
fun box apply(
  event_log: EventLog tag,
  auth: AmbientAuth val,
  new_proxy_router: ProxyRouter val,
  boundary2: OutgoingBoundary tag,
  boundary3: OutgoingBoundary tag)
: HashMap[String val, (Step tag | ProxyRouter val), HashEq[String val] val] val
```
#### Parameters

*   event_log: [EventLog](wallaroo-ent-recovery-EventLog) tag
*   auth: [AmbientAuth](builtin-AmbientAuth) val
*   new_proxy_router: [ProxyRouter](wallaroo-core-topology-ProxyRouter) val
*   boundary2: [OutgoingBoundary](wallaroo-core-boundary-OutgoingBoundary) tag
*   boundary3: [OutgoingBoundary](wallaroo-core-boundary-OutgoingBoundary) tag

#### Returns

* [HashMap](collections-HashMap)\[[String](builtin-String) val, ([Step](wallaroo-core-topology-Step) tag | [ProxyRouter](wallaroo-core-topology-ProxyRouter) val), [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val

---

### eq

```pony
fun box eq(
  that: _TargetPartitionRoutesGenerator val)
: Bool val
```
#### Parameters

*   that: [_TargetPartitionRoutesGenerator](wallaroo-core-topology-_TargetPartitionRoutesGenerator) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: _TargetPartitionRoutesGenerator val)
: Bool val
```
#### Parameters

*   that: [_TargetPartitionRoutesGenerator](wallaroo-core-topology-_TargetPartitionRoutesGenerator) val

#### Returns

* [Bool](builtin-Bool) val

---

