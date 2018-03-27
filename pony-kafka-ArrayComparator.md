# ArrayComparator\[A: ([Equatable](builtin-Equatable)\[A\] #read & [Stringable](builtin-Stringable) #read)\]

```pony
primitive val ArrayComparator[A: (Equatable[A] #read & Stringable #read)]
```

## Constructors

### create

```pony
new val create()
: ArrayComparator[A] val^
```

#### Returns

* [ArrayComparator](pony-kafka-ArrayComparator)\[A\] val^

---

## Public Functions

### eq

```pony
fun box eq(
  a: Array[A] ref,
  b: Array[A] ref)
: Bool val ?
```
#### Parameters

*   a: [Array](builtin-Array)\[A\] ref
*   b: [Array](builtin-Array)\[A\] ref

#### Returns

* [Bool](builtin-Bool) val ?

---

### ne

```pony
fun box ne(
  that: ArrayComparator[A] val)
: Bool val
```
#### Parameters

*   that: [ArrayComparator](pony-kafka-ArrayComparator)\[A\] val

#### Returns

* [Bool](builtin-Bool) val

---

