# QueuePairs\[A: A, B: [Array](builtin-Array)\[A\] #read\]

```pony
class ref QueuePairs[A: A, B: Array[A] #read] is
  Iterator[(USize val , B->A)] ref
```

#### Implements

* [Iterator](builtin-Iterator)\[([USize](builtin-USize) val , B->A)\] ref

---

## Constructors

### create

```pony
new ref create(
  data: B,
  front: USize val,
  back: USize val)
: QueuePairs[A, B] ref^
```
#### Parameters

*   data: B
*   front: [USize](builtin-USize) val
*   back: [USize](builtin-USize) val

#### Returns

* [QueuePairs](wallaroo_labs-queue-QueuePairs)\[A, B\] ref^

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
: (USize val , B->A) ?
```

#### Returns

* ([USize](builtin-USize) val , B->A) ?

---

