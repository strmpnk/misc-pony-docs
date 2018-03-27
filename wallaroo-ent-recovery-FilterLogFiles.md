# FilterLogFiles

```pony
primitive val FilterLogFiles
```

## Constructors

### create

```pony
new val create()
: FilterLogFiles val^
```

#### Returns

* [FilterLogFiles](wallaroo-ent-recovery-FilterLogFiles) val^

---

## Public Functions

### apply

```pony
fun box apply(
  base_name: String val,
  suffix: String val = seq,
  entries: Array[String val] iso)
: Array[String val] ref
```
#### Parameters

*   base_name: [String](builtin-String) val
*   suffix: [String](builtin-String) val = seq
*   entries: [Array](builtin-Array)\[[String](builtin-String) val\] iso

#### Returns

* [Array](builtin-Array)\[[String](builtin-String) val\] ref

---

### eq

```pony
fun box eq(
  that: FilterLogFiles val)
: Bool val
```
#### Parameters

*   that: [FilterLogFiles](wallaroo-ent-recovery-FilterLogFiles) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: FilterLogFiles val)
: Bool val
```
#### Parameters

*   that: [FilterLogFiles](wallaroo-ent-recovery-FilterLogFiles) val

#### Returns

* [Bool](builtin-Bool) val

---

