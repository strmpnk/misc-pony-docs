# Queue\[A: [Any](builtin-Any)\]

```pony
class ref Queue[A: Any]
```

## Constructors

### create

```pony
new ref create(
  len: USize val = seq)
: Queue[A] ref^
```
#### Parameters

*   len: [USize](builtin-USize) val = seq

#### Returns

* [Queue](wallaroo_labs-queue-Queue)\[A\] ref^

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

Add an element to the back of the queue, doubling the allocation
if the queue size has reached the allocated size and shifting any
wrapping elements to the end of a contiguous series.


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
: Queue[A] ref^
```

#### Returns

* [Queue](wallaroo_labs-queue-Queue)\[A\] ref^

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

### values

```pony
fun box values()
: QueueValues[A, this->Array[A] ref] ref^
```

#### Returns

* [QueueValues](wallaroo_labs-queue-QueueValues)\[A, this->[Array](builtin-Array)\[A\] ref\] ref^

---

### pairs

```pony
fun box pairs()
: QueuePairs[A, this->Array[A] ref] ref^
```

#### Returns

* [QueuePairs](wallaroo_labs-queue-QueuePairs)\[A, this->[Array](builtin-Array)\[A\] ref\] ref^

---

## Private Functions

### _update

Change the i-th element, raising an error if the index is out of bounds.


```pony
fun ref _update(
  i: USize val,
  value: A)
: A^ ?
```
#### Parameters

*   i: [USize](builtin-USize) val
*   value: A

#### Returns

* A^ ?

---

