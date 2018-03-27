# MessageDeduplicator

```pony
primitive val MessageDeduplicator
```

## Constructors

### create

```pony
new val create()
: MessageDeduplicator val^
```

#### Returns

* [MessageDeduplicator](wallaroo-ent-recovery-MessageDeduplicator) val^

---

## Public Functions

### is_duplicate

```pony
fun box is_duplicate(
  msg_uid: U128 val,
  frac_ids: (Array[U32 val] val | None val),
  list: Array[(U128 val , (Array[U32 val] val | None val))] ref)
: Bool val
```
#### Parameters

*   msg_uid: [U128](builtin-U128) val
*   frac_ids: ([Array](builtin-Array)\[[U32](builtin-U32) val\] val | [None](builtin-None) val)
*   list: [Array](builtin-Array)\[([U128](builtin-U128) val , ([Array](builtin-Array)\[[U32](builtin-U32) val\] val | [None](builtin-None) val))\] ref

#### Returns

* [Bool](builtin-Bool) val

---

### eq

```pony
fun box eq(
  that: MessageDeduplicator val)
: Bool val
```
#### Parameters

*   that: [MessageDeduplicator](wallaroo-ent-recovery-MessageDeduplicator) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: MessageDeduplicator val)
: Bool val
```
#### Parameters

*   that: [MessageDeduplicator](wallaroo-ent-recovery-MessageDeduplicator) val

#### Returns

* [Bool](builtin-Bool) val

---

## Private Functions

### _individual_match

```pony
fun box _individual_match(
  check: (U128 val , (Array[U32 val] val | None val)),
  against: (U128 val , (Array[U32 val] val | None val)))
: Bool val
```
#### Parameters

*   check: ([U128](builtin-U128) val , ([Array](builtin-Array)\[[U32](builtin-U32) val\] val | [None](builtin-None) val))
*   against: ([U128](builtin-U128) val , ([Array](builtin-Array)\[[U32](builtin-U32) val\] val | [None](builtin-None) val))

#### Returns

* [Bool](builtin-Bool) val

---

