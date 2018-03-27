# _IdMapGenerator

```pony
primitive val _IdMapGenerator
```

## Constructors

### create

```pony
new val create()
: _IdMapGenerator val^
```

#### Returns

* [_IdMapGenerator](wallaroo-core-initialization-_IdMapGenerator) val^

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
  that: _IdMapGenerator val)
: Bool val
```
#### Parameters

*   that: [_IdMapGenerator](wallaroo-core-initialization-_IdMapGenerator) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: _IdMapGenerator val)
: Bool val
```
#### Parameters

*   that: [_IdMapGenerator](wallaroo-core-initialization-_IdMapGenerator) val

#### Returns

* [Bool](builtin-Bool) val

---

