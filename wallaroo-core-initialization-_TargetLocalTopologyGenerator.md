# _TargetLocalTopologyGenerator

```pony
primitive val _TargetLocalTopologyGenerator
```

## Constructors

### create

```pony
new val create()
: _TargetLocalTopologyGenerator val^
```

#### Returns

* [_TargetLocalTopologyGenerator](wallaroo-core-initialization-_TargetLocalTopologyGenerator) val^

---

## Public Functions

### apply

```pony
fun box apply(
  dag: Dag[(StepBuilder val | SourceData val | EgressBuilder val | PreStatelessData val)] val,
  psd: Array[PreStateData val] val,
  pf: PartitionFunction[String val, String val] val,
  rb: RunnerBuilder val)
: LocalTopology val
```
#### Parameters

*   dag: [Dag](wallaroo_labs-dag-Dag)\[([StepBuilder](wallaroo-core-topology-StepBuilder) val | [SourceData](wallaroo-core-topology-SourceData) val | [EgressBuilder](wallaroo-core-topology-EgressBuilder) val | [PreStatelessData](wallaroo-core-topology-PreStatelessData) val)\] val
*   psd: [Array](builtin-Array)\[[PreStateData](wallaroo-core-topology-PreStateData) val\] val
*   pf: [PartitionFunction](wallaroo-core-topology-PartitionFunction)\[[String](builtin-String) val, [String](builtin-String) val\] val
*   rb: [RunnerBuilder](wallaroo-core-topology-RunnerBuilder) val

#### Returns

* [LocalTopology](wallaroo-core-initialization-LocalTopology) val

---

### eq

```pony
fun box eq(
  that: _TargetLocalTopologyGenerator val)
: Bool val
```
#### Parameters

*   that: [_TargetLocalTopologyGenerator](wallaroo-core-initialization-_TargetLocalTopologyGenerator) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: _TargetLocalTopologyGenerator val)
: Bool val
```
#### Parameters

*   that: [_TargetLocalTopologyGenerator](wallaroo-core-initialization-_TargetLocalTopologyGenerator) val

#### Returns

* [Bool](builtin-Bool) val

---

