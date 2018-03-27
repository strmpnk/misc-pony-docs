# _EmptyIter\[A: A\]

```pony
class ref _EmptyIter[A: A]
```

## Constructors

### create

```pony
new iso create()
: _EmptyIter[A] iso^
```

#### Returns

* [_EmptyIter](itertools-_EmptyIter)\[A\] iso^

---

## Public Functions

### has_next

```pony
fun ref has_next()
: Bool val
```

#### Returns

* [Bool](builtin-Bool) val

---

### next

```pony
fun ref next()
: A ?
```

#### Returns

* A ?

---

