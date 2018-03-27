# _BaseStateSubpartitionGenerator

```pony
primitive val _BaseStateSubpartitionGenerator
```

## Constructors

### create

```pony
new val create()
: _BaseStateSubpartitionGenerator val^
```

#### Returns

* [_BaseStateSubpartitionGenerator](wallaroo-core-initialization-_BaseStateSubpartitionGenerator) val^

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
  that: _BaseStateSubpartitionGenerator val)
: Bool val
```
#### Parameters

*   that: [_BaseStateSubpartitionGenerator](wallaroo-core-initialization-_BaseStateSubpartitionGenerator) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: _BaseStateSubpartitionGenerator val)
: Bool val
```
#### Parameters

*   that: [_BaseStateSubpartitionGenerator](wallaroo-core-initialization-_BaseStateSubpartitionGenerator) val

#### Returns

* [Bool](builtin-Bool) val

---

