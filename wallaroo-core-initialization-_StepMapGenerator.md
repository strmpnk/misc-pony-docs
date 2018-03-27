# _StepMapGenerator

```pony
primitive val _StepMapGenerator
```

## Constructors

### create

```pony
new val create()
: _StepMapGenerator val^
```

#### Returns

* [_StepMapGenerator](wallaroo-core-initialization-_StepMapGenerator) val^

---

## Public Functions

### apply

```pony
fun box apply()
: HashMap[U128 val, (ProxyAddress val | U128 val), HashEq[U128 val] val] val
```

#### Returns

* [HashMap](collections-HashMap)\[[U128](builtin-U128) val, ([ProxyAddress](wallaroo-core-topology-ProxyAddress) val | [U128](builtin-U128) val), [HashEq](collections-HashEq)\[[U128](builtin-U128) val\] val\] val

---

### eq

```pony
fun box eq(
  that: _StepMapGenerator val)
: Bool val
```
#### Parameters

*   that: [_StepMapGenerator](wallaroo-core-initialization-_StepMapGenerator) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: _StepMapGenerator val)
: Bool val
```
#### Parameters

*   that: [_StepMapGenerator](wallaroo-core-initialization-_StepMapGenerator) val

#### Returns

* [Bool](builtin-Bool) val

---

