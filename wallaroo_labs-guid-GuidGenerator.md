# GuidGenerator

```pony
class ref GuidGenerator
```

## Constructors

### create

```pony
new ref create(
  seed: U64 val = seq)
: GuidGenerator ref^
```
#### Parameters

*   seed: [U64](builtin-U64) val = seq

#### Returns

* [GuidGenerator](wallaroo_labs-guid-GuidGenerator) ref^

---

## Public Functions

### apply

```pony
fun ref apply()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### u128

```pony
fun ref u128()
: U128 val
```

#### Returns

* [U128](builtin-U128) val

---

### u64

```pony
fun ref u64()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

