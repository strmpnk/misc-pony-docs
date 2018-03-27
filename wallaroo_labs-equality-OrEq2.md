# OrEq2\[A: [Equatable](builtin-Equatable)\[A\] #read, B: [Equatable](builtin-Equatable)\[B\] #read\]

```pony
primitive val OrEq2[A: Equatable[A] #read, B: Equatable[B] #read]
```

## Constructors

### create

```pony
new val create()
: OrEq2[A, B] val^
```

#### Returns

* [OrEq2](wallaroo_labs-equality-OrEq2)\[A, B\] val^

---

## Public Functions

### apply

```pony
fun box apply(
  v1: (box->A | box->B),
  v2: (box->A | box->B))
: Bool val
```
#### Parameters

*   v1: (box->A | box->B)
*   v2: (box->A | box->B)

#### Returns

* [Bool](builtin-Bool) val

---

### eq

```pony
fun box eq(
  that: OrEq2[A, B] val)
: Bool val
```
#### Parameters

*   that: [OrEq2](wallaroo_labs-equality-OrEq2)\[A, B\] val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: OrEq2[A, B] val)
: Bool val
```
#### Parameters

*   that: [OrEq2](wallaroo_labs-equality-OrEq2)\[A, B\] val

#### Returns

* [Bool](builtin-Bool) val

---

