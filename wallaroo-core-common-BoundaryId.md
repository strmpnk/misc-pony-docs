# BoundaryId

```pony
class ref BoundaryId is
  Equatable[BoundaryId ref] ref
```

#### Implements

* [Equatable](builtin-Equatable)\[[BoundaryId](wallaroo-core-common-BoundaryId) ref\] ref

---

## Constructors

### create

```pony
new ref create(
  n: String val,
  s_id: U128 val)
: BoundaryId ref^
```
#### Parameters

*   n: [String](builtin-String) val
*   s_id: [U128](builtin-U128) val

#### Returns

* [BoundaryId](wallaroo-core-common-BoundaryId) ref^

---

## Public fields

* let name: [String](builtin-String) val

---

* let step_id: [U128](builtin-U128) val

---

## Public Functions

### eq

```pony
fun box eq(
  that: BoundaryId box)
: Bool val
```
#### Parameters

*   that: [BoundaryId](wallaroo-core-common-BoundaryId) box

#### Returns

* [Bool](builtin-Bool) val

---

### hash

```pony
fun box hash()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### ne

```pony
fun box ne(
  that: BoundaryId box)
: Bool val
```
#### Parameters

*   that: [BoundaryId](wallaroo-core-common-BoundaryId) box

#### Returns

* [Bool](builtin-Bool) val

---

