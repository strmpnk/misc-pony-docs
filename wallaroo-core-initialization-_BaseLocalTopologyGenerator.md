# _BaseLocalTopologyGenerator

```pony
primitive val _BaseLocalTopologyGenerator
```

## Constructors

### create

```pony
new val create()
: _BaseLocalTopologyGenerator val^
```

#### Returns

* [_BaseLocalTopologyGenerator](wallaroo-core-initialization-_BaseLocalTopologyGenerator) val^

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
  that: _BaseLocalTopologyGenerator val)
: Bool val
```
#### Parameters

*   that: [_BaseLocalTopologyGenerator](wallaroo-core-initialization-_BaseLocalTopologyGenerator) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: _BaseLocalTopologyGenerator val)
: Bool val
```
#### Parameters

*   that: [_BaseLocalTopologyGenerator](wallaroo-core-initialization-_BaseLocalTopologyGenerator) val

#### Returns

* [Bool](builtin-Bool) val

---

