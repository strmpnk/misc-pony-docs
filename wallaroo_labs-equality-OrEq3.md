# OrEq3\[A: [Equatable](builtin-Equatable)\[A\] #read, B: [Equatable](builtin-Equatable)\[B\] #read, C: [Equatable](builtin-Equatable)\[C\] #read\]

```pony
primitive val OrEq3[A: Equatable[A] #read, B: Equatable[B] #read, C: Equatable[C] #read]
```

## Constructors

### create

```pony
new val create()
: OrEq3[A, B, C] val^
```

#### Returns

* [OrEq3](wallaroo_labs-equality-OrEq3)\[A, B, C\] val^

---

## Public Functions

### apply

```pony
fun box apply(
  v1: (box->A | box->B | box->C),
  v2: (box->A | box->B | box->C))
: Bool val
```
#### Parameters

*   v1: (box->A | box->B | box->C)
*   v2: (box->A | box->B | box->C)

#### Returns

* [Bool](builtin-Bool) val

---

### eq

```pony
fun box eq(
  that: OrEq3[A, B, C] val)
: Bool val
```
#### Parameters

*   that: [OrEq3](wallaroo_labs-equality-OrEq3)\[A, B, C\] val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: OrEq3[A, B, C] val)
: Bool val
```
#### Parameters

*   that: [OrEq3](wallaroo_labs-equality-OrEq3)\[A, B, C\] val

#### Returns

* [Bool](builtin-Bool) val

---

