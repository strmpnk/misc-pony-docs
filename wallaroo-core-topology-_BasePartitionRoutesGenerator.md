# _BasePartitionRoutesGenerator

```pony
primitive val _BasePartitionRoutesGenerator
```

## Constructors

### create

```pony
new val create()
: _BasePartitionRoutesGenerator val^
```

#### Returns

* [_BasePartitionRoutesGenerator](wallaroo-core-topology-_BasePartitionRoutesGenerator) val^

---

## Public Functions

### apply

```pony
fun box apply(
  event_log: EventLog tag,
  auth: AmbientAuth val,
  step1: Step tag,
  boundary2: OutgoingBoundary tag,
  boundary3: OutgoingBoundary tag)
: HashMap[String val, (Step tag | ProxyRouter val), HashEq[String val] val] val
```
#### Parameters

*   event_log: [EventLog](wallaroo-ent-recovery-EventLog) tag
*   auth: [AmbientAuth](builtin-AmbientAuth) val
*   step1: [Step](wallaroo-core-topology-Step) tag
*   boundary2: [OutgoingBoundary](wallaroo-core-boundary-OutgoingBoundary) tag
*   boundary3: [OutgoingBoundary](wallaroo-core-boundary-OutgoingBoundary) tag

#### Returns

* [HashMap](collections-HashMap)\[[String](builtin-String) val, ([Step](wallaroo-core-topology-Step) tag | [ProxyRouter](wallaroo-core-topology-ProxyRouter) val), [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val

---

### eq

```pony
fun box eq(
  that: _BasePartitionRoutesGenerator val)
: Bool val
```
#### Parameters

*   that: [_BasePartitionRoutesGenerator](wallaroo-core-topology-_BasePartitionRoutesGenerator) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: _BasePartitionRoutesGenerator val)
: Bool val
```
#### Parameters

*   that: [_BasePartitionRoutesGenerator](wallaroo-core-topology-_BasePartitionRoutesGenerator) val

#### Returns

* [Bool](builtin-Bool) val

---

