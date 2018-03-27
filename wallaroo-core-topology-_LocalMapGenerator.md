# _LocalMapGenerator

```pony
primitive val _LocalMapGenerator
```

## Constructors

### create

```pony
new val create()
: _LocalMapGenerator val^
```

#### Returns

* [_LocalMapGenerator](wallaroo-core-topology-_LocalMapGenerator) val^

---

## Public Functions

### apply

```pony
fun box apply()
: HashMap[U128 val, Step tag, HashEq[U128 val] val] val
```

#### Returns

* [HashMap](collections-HashMap)\[[U128](builtin-U128) val, [Step](wallaroo-core-topology-Step) tag, [HashEq](collections-HashEq)\[[U128](builtin-U128) val\] val\] val

---

### eq

```pony
fun box eq(
  that: _LocalMapGenerator val)
: Bool val
```
#### Parameters

*   that: [_LocalMapGenerator](wallaroo-core-topology-_LocalMapGenerator) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: _LocalMapGenerator val)
: Bool val
```
#### Parameters

*   that: [_LocalMapGenerator](wallaroo-core-topology-_LocalMapGenerator) val

#### Returns

* [Bool](builtin-Bool) val

---

