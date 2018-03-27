# _TargetStateSubpartitionGenerator

```pony
primitive val _TargetStateSubpartitionGenerator
```

## Constructors

### create

```pony
new val create()
: _TargetStateSubpartitionGenerator val^
```

#### Returns

* [_TargetStateSubpartitionGenerator](wallaroo-core-initialization-_TargetStateSubpartitionGenerator) val^

---

## Public Functions

### apply

```pony
fun box apply(
  rb: RunnerBuilder val,
  pf: PartitionFunction[String val, String val] val)
: StateSubpartition val
```
#### Parameters

*   rb: [RunnerBuilder](wallaroo-core-topology-RunnerBuilder) val
*   pf: [PartitionFunction](wallaroo-core-topology-PartitionFunction)\[[String](builtin-String) val, [String](builtin-String) val\] val

#### Returns

* [StateSubpartition](wallaroo-core-topology-StateSubpartition) val

---

### eq

```pony
fun box eq(
  that: _TargetStateSubpartitionGenerator val)
: Bool val
```
#### Parameters

*   that: [_TargetStateSubpartitionGenerator](wallaroo-core-initialization-_TargetStateSubpartitionGenerator) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: _TargetStateSubpartitionGenerator val)
: Bool val
```
#### Parameters

*   that: [_TargetStateSubpartitionGenerator](wallaroo-core-initialization-_TargetStateSubpartitionGenerator) val

#### Returns

* [Bool](builtin-Bool) val

---

