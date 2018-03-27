# _FilteredOnStep

Class to keep track of highest message sequence id for this step acker.


```pony
class ref _FilteredOnStep
```

## Constructors

### create

```pony
new iso create()
: _FilteredOnStep iso^
```

#### Returns

* [_FilteredOnStep](wallaroo-ent-watermarking-_FilteredOnStep) iso^

---

## Public Functions

### filtered

```pony
fun ref filtered(
  o_seq_id: U64 val)
: None val
```
#### Parameters

*   o_seq_id: [U64](builtin-U64) val

#### Returns

* [None](builtin-None) val

---

### is_fully_acked

```pony
fun box is_fully_acked()
: Bool val
```

#### Returns

* [Bool](builtin-Bool) val

---

### highest_seq_id

```pony
fun box highest_seq_id()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

