# _BaseStateBuildersGenerator

```pony
primitive val _BaseStateBuildersGenerator
```

## Constructors

### create

```pony
new val create()
: _BaseStateBuildersGenerator val^
```

#### Returns

* [_BaseStateBuildersGenerator](wallaroo-core-initialization-_BaseStateBuildersGenerator) val^

---

## Public Functions

### apply

```pony
fun box apply(
  rb: RunnerBuilder val,
  pf: PartitionFunction[String val, String val] val)
: HashMap[String val, StateSubpartition val, HashEq[String val] val] val
```
#### Parameters

*   rb: [RunnerBuilder](wallaroo-core-topology-RunnerBuilder) val
*   pf: [PartitionFunction](wallaroo-core-topology-PartitionFunction)\[[String](builtin-String) val, [String](builtin-String) val\] val

#### Returns

* [HashMap](collections-HashMap)\[[String](builtin-String) val, [StateSubpartition](wallaroo-core-topology-StateSubpartition) val, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val

---

### eq

```pony
fun box eq(
  that: _BaseStateBuildersGenerator val)
: Bool val
```
#### Parameters

*   that: [_BaseStateBuildersGenerator](wallaroo-core-initialization-_BaseStateBuildersGenerator) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: _BaseStateBuildersGenerator val)
: Bool val
```
#### Parameters

*   that: [_BaseStateBuildersGenerator](wallaroo-core-initialization-_BaseStateBuildersGenerator) val

#### Returns

* [Bool](builtin-Bool) val

---

