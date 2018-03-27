# _Then\[A: [Any](builtin-Any) #share, B: [Any](builtin-Any) #share\]

A step in a promise pipeline.


```pony
class ref _Then[A: Any #share, B: Any #share]
```

## Constructors

### create

```pony
new iso create(
  fulfill: Fulfill[A, B] iso,
  rejected: Reject[B] iso)
: _Then[A, B] iso^
```
#### Parameters

*   fulfill: [Fulfill](promises-Fulfill)\[A, B\] iso
*   rejected: [Reject](promises-Reject)\[B\] iso

#### Returns

* [_Then](promises-_Then)\[A, B\] iso^

---

## Public Functions

### promise

Returns the next promise in the chain.


```pony
fun box promise()
: Promise[B] tag
```

#### Returns

* [Promise](promises-Promise)\[B\] tag

---

### apply

Called with the result of the previous promise when it is fulfilled.


```pony
fun ref apply(
  value: A)
: None val
```
#### Parameters

*   value: A

#### Returns

* [None](builtin-None) val

---

### reject

Called when the previous promise is rejected.


```pony
fun ref reject()
: None val
```

#### Returns

* [None](builtin-None) val

---

