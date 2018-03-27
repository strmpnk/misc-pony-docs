# _DagGenerator

```pony
primitive val _DagGenerator
```

## Constructors

### create

```pony
new val create()
: _DagGenerator val^
```

#### Returns

* [_DagGenerator](wallaroo-core-initialization-_DagGenerator) val^

---

## Public Functions

### apply

```pony
fun box apply()
: Dag[(StepBuilder val | SourceData val | EgressBuilder val | PreStatelessData val)] val
```

#### Returns

* [Dag](wallaroo_labs-dag-Dag)\[([StepBuilder](wallaroo-core-topology-StepBuilder) val | [SourceData](wallaroo-core-topology-SourceData) val | [EgressBuilder](wallaroo-core-topology-EgressBuilder) val | [PreStatelessData](wallaroo-core-topology-PreStatelessData) val)\] val

---

### eq

```pony
fun box eq(
  that: _DagGenerator val)
: Bool val
```
#### Parameters

*   that: [_DagGenerator](wallaroo-core-initialization-_DagGenerator) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: _DagGenerator val)
: Bool val
```
#### Parameters

*   that: [_DagGenerator](wallaroo-core-initialization-_DagGenerator) val

#### Returns

* [Bool](builtin-Bool) val

---

