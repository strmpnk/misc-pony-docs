# CheckCounts\[Key: ([Hashable](collections-Hashable) #read & [Equatable](builtin-Equatable)\[Key\] #read), Counted: Counted\]

```pony
primitive val CheckCounts[Key: (Hashable #read & Equatable[Key] #read), Counted: Counted]
```

## Constructors

### create

```pony
new val create()
: CheckCounts[Key, Counted] val^
```

#### Returns

* [CheckCounts](wallaroo-ent-recovery-CheckCounts)\[Key, Counted\] val^

---

## Public Functions

### apply

```pony
fun box apply(
  expected_counts: HashMap[Key, USize val, HashEq[Key] val] box,
  counted: HashMap[Key, HashSet[Counted, HashIs[Counted!] val] ref, HashEq[Key] val] box)
: Bool val
```
#### Parameters

*   expected_counts: [HashMap](collections-HashMap)\[Key, [USize](builtin-USize) val, [HashEq](collections-HashEq)\[Key\] val\] box
*   counted: [HashMap](collections-HashMap)\[Key, [HashSet](collections-HashSet)\[Counted, [HashIs](collections-HashIs)\[Counted!\] val\] ref, [HashEq](collections-HashEq)\[Key\] val\] box

#### Returns

* [Bool](builtin-Bool) val

---

### eq

```pony
fun box eq(
  that: CheckCounts[Key, Counted] val)
: Bool val
```
#### Parameters

*   that: [CheckCounts](wallaroo-ent-recovery-CheckCounts)\[Key, Counted\] val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: CheckCounts[Key, Counted] val)
: Bool val
```
#### Parameters

*   that: [CheckCounts](wallaroo-ent-recovery-CheckCounts)\[Key, Counted\] val

#### Returns

* [Bool](builtin-Bool) val

---

