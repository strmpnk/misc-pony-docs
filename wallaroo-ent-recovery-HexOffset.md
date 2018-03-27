# HexOffset

```pony
primitive val HexOffset
```

## Constructors

### create

```pony
new val create()
: HexOffset val^
```

#### Returns

* [HexOffset](wallaroo-ent-recovery-HexOffset) val^

---

## Public Functions

### apply

```pony
fun box apply(
  offset: U64 val)
: String iso^
```
#### Parameters

*   offset: [U64](builtin-U64) val

#### Returns

* [String](builtin-String) iso^

---

### u64

```pony
fun box u64(
  hex: String val)
: U64 val ?
```
#### Parameters

*   hex: [String](builtin-String) val

#### Returns

* [U64](builtin-U64) val ?

---

### eq

```pony
fun box eq(
  that: HexOffset val)
: Bool val
```
#### Parameters

*   that: [HexOffset](wallaroo-ent-recovery-HexOffset) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: HexOffset val)
: Bool val
```
#### Parameters

*   that: [HexOffset](wallaroo-ent-recovery-HexOffset) val

#### Returns

* [Bool](builtin-Bool) val

---

