# _Join\[A: [Any](builtin-Any) #share\]

```pony
actor tag _Join[A: Any #share]
```

## Constructors

### create

```pony
new tag create(
  p: Promise[Array[A] val] tag,
  space: USize val)
: _Join[A] tag^
```
#### Parameters

*   p: [Promise](promises-Promise)\[[Array](builtin-Array)\[A\] val\] tag
*   space: [USize](builtin-USize) val

#### Returns

* [_Join](promises-_Join)\[A\] tag^

---

## Public Behaviours

### apply

```pony
be apply(
  a: A)
```
#### Parameters

*   a: A

---

