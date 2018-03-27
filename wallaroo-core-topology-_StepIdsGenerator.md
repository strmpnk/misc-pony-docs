# _StepIdsGenerator

```pony
primitive val _StepIdsGenerator
```

## Constructors

### create

```pony
new val create()
: _StepIdsGenerator val^
```

#### Returns

* [_StepIdsGenerator](wallaroo-core-topology-_StepIdsGenerator) val^

---

## Public Functions

### apply

```pony
fun box apply()
: HashMap[String val, U128 val, HashEq[String val] val] val
```

#### Returns

* [HashMap](collections-HashMap)\[[String](builtin-String) val, [U128](builtin-U128) val, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] val

---

### eq

```pony
fun box eq(
  that: _StepIdsGenerator val)
: Bool val
```
#### Parameters

*   that: [_StepIdsGenerator](wallaroo-core-topology-_StepIdsGenerator) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: _StepIdsGenerator val)
: Bool val
```
#### Parameters

*   that: [_StepIdsGenerator](wallaroo-core-topology-_StepIdsGenerator) val

#### Returns

* [Bool](builtin-Bool) val

---

