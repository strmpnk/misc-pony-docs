# DagNode\[V: [Any](builtin-Any) val\]

```pony
class ref DagNode[V: Any val]
```

## Constructors

### create

```pony
new ref create(
  v: V,
  id': U128 val)
: DagNode[V] ref^
```
#### Parameters

*   v: V
*   id': [U128](builtin-U128) val

#### Returns

* [DagNode](wallaroo_labs-dag-DagNode)\[V\] ref^

---

## Public fields

* let id: [U128](builtin-U128) val

---

* let value: V

---

## Public Functions

### add_input

```pony
fun ref add_input(
  input: DagNode[V] ref)
: None val
```
#### Parameters

*   input: [DagNode](wallaroo_labs-dag-DagNode)\[V\] ref

#### Returns

* [None](builtin-None) val

---

### add_output

```pony
fun ref add_output(
  output: DagNode[V] ref)
: None val
```
#### Parameters

*   output: [DagNode](wallaroo_labs-dag-DagNode)\[V\] ref

#### Returns

* [None](builtin-None) val

---

### has_input_from

```pony
fun box has_input_from(
  node: DagNode[V] ref)
: Bool val
```
#### Parameters

*   node: [DagNode](wallaroo_labs-dag-DagNode)\[V\] ref

#### Returns

* [Bool](builtin-Bool) val

---

### has_output_from

```pony
fun box has_output_from(
  node: DagNode[V] ref)
: Bool val
```
#### Parameters

*   node: [DagNode](wallaroo_labs-dag-DagNode)\[V\] ref

#### Returns

* [Bool](builtin-Bool) val

---

### ins

```pony
fun box ins()
: Iterator[this->DagNode[V] ref] ref
```

#### Returns

* [Iterator](builtin-Iterator)\[this->[DagNode](wallaroo_labs-dag-DagNode)\[V\] ref\] ref

---

### outs

```pony
fun box outs()
: Iterator[this->DagNode[V] ref] ref
```

#### Returns

* [Iterator](builtin-Iterator)\[this->[DagNode](wallaroo_labs-dag-DagNode)\[V\] ref\] ref

---

### is_source

```pony
fun box is_source()
: Bool val
```

#### Returns

* [Bool](builtin-Bool) val

---

### is_sink

```pony
fun box is_sink()
: Bool val
```

#### Returns

* [Bool](builtin-Bool) val

---

