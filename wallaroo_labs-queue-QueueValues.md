# QueueValues\[A: A, B: [Array](builtin-Array)\[A\] #read\]

```pony
class ref QueueValues[A: A, B: Array[A] #read] is
  Iterator[B->A] ref
```

#### Implements

* [Iterator](builtin-Iterator)\[B->A\] ref

---

## Constructors

### create

```pony
new ref create(
  data: B,
  front: USize val,
  back: USize val)
: QueueValues[A, B] ref^
```
#### Parameters

*   data: B
*   front: [USize](builtin-USize) val
*   back: [USize](builtin-USize) val

#### Returns

* [QueueValues](wallaroo_labs-queue-QueueValues)\[A, B\] ref^

---

## Public Functions

### has_next

```pony
fun box has_next()
: Bool val
```

#### Returns

* [Bool](builtin-Bool) val

---

### next

```pony
fun ref next()
: B->A ?
```

#### Returns

* B->A ?

---

### rewind

```pony
fun ref rewind()
: QueueValues[A, B] ref
```

#### Returns

* [QueueValues](wallaroo_labs-queue-QueueValues)\[A, B\] ref

---

