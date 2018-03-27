# FixedQueue\[A: A\]

```pony
class ref FixedQueue[A: A]
```

## Constructors

### create

```pony
new ref create(
  len: USize val)
: FixedQueue[A] ref^
```
#### Parameters

*   len: [USize](builtin-USize) val

#### Returns

* [FixedQueue](wallaroo_labs-queue-FixedQueue)\[A\] ref^

---

## Public Functions

### size

The size of the queue.


```pony
fun box size()
: USize val
```

#### Returns

* [USize](builtin-USize) val

---

### max_size

The max size of the queue.


```pony
fun box max_size()
: USize val
```

#### Returns

* [USize](builtin-USize) val

---

### space

```pony
fun box space()
: USize val
```

#### Returns

* [USize](builtin-USize) val

---

### apply

Get the i-th element from the front of the queue,
raising an error if the index is out of bounds.


```pony
fun box apply(
  i: USize val)
: this->A ?
```
#### Parameters

*   i: [USize](builtin-USize) val

#### Returns

* this->A ?

---

### enqueue

Add an element to the back of the queue


```pony
fun ref enqueue(
  a: A)
: None val ?
```
#### Parameters

*   a: A

#### Returns

* [None](builtin-None) val ?

---

### dequeue

```pony
fun ref dequeue()
: A! ?
```

#### Returns

* A! ?

---

### peek

```pony
fun box peek()
: this->A ?
```

#### Returns

* this->A ?

---

### clear

Remove all elements from the queue.
The queue is returned to allow call chaining.


```pony
fun ref clear()
: FixedQueue[A] ref^
```

#### Returns

* [FixedQueue](wallaroo_labs-queue-FixedQueue)\[A\] ref^

---

### clear_n

```pony
fun ref clear_n(
  n: USize val)
: None val
```
#### Parameters

*   n: [USize](builtin-USize) val

#### Returns

* [None](builtin-None) val

---

### contains

Returns true if the queue contains `value`, false otherwise.


```pony
fun box contains(
  a: A!,
  pred: {(box->A!, box->A!): Bool}[A] val = seq)
: Bool val
```
#### Parameters

*   a: A!
*   pred: {(box->A!, box->A!): Bool}[A] val = seq

#### Returns

* [Bool](builtin-Bool) val

---

