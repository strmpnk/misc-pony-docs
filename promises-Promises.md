# Promises\[A: [Any](builtin-Any) #share\]

```pony
primitive val Promises[A: Any #share]
```

## Constructors

### create

```pony
new val create()
: Promises[A] val^
```

#### Returns

* [Promises](promises-Promises)\[A\] val^

---

## Public Functions

### join

Create a promise that is fulfilled when all promises in the given sequence
are fulfilled. If any promise in the sequence is rejected then the new
promise is also rejected. The order that values appear in the final array
is based on when each promise is fulfilled and not the order that they are
given.


```pony
fun box join(
  ps: Iterator[Promise[A] tag] ref)
: Promise[Array[A] val] tag
```
#### Parameters

*   ps: [Iterator](builtin-Iterator)\[[Promise](promises-Promise)\[A\] tag\] ref

#### Returns

* [Promise](promises-Promise)\[[Array](builtin-Array)\[A\] val\] tag

---

### eq

```pony
fun box eq(
  that: Promises[A] val)
: Bool val
```
#### Parameters

*   that: [Promises](promises-Promises)\[A\] val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: Promises[A] val)
: Bool val
```
#### Parameters

*   that: [Promises](promises-Promises)\[A\] val

#### Returns

* [Bool](builtin-Bool) val

---

