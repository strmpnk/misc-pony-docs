# Dag\[V: [Any](builtin-Any) val\]

```pony
class ref Dag[V: Any val]
```

## Constructors

### create

```pony
new iso create()
: Dag[V] iso^
```

#### Returns

* [Dag](wallaroo_labs-dag-Dag)\[V\] iso^

---

## Public Functions

### add_node

```pony
fun ref add_node(
  value: V,
  id': U128 val = seq)
: U128 val
```
#### Parameters

*   value: V
*   id': [U128](builtin-U128) val = seq

#### Returns

* [U128](builtin-U128) val

---

### contains

```pony
fun box contains(
  id: U128 val)
: Bool val
```
#### Parameters

*   id: [U128](builtin-U128) val

#### Returns

* [Bool](builtin-Bool) val

---

### get_node

```pony
fun box get_node(
  id: U128 val)
: this->DagNode[V] ref ?
```
#### Parameters

*   id: [U128](builtin-U128) val

#### Returns

* this->[DagNode](wallaroo_labs-dag-DagNode)\[V\] ref ?

---

### nodes

```pony
fun box nodes()
: Iterator[this->DagNode[V] ref] ref
```

#### Returns

* [Iterator](builtin-Iterator)\[this->[DagNode](wallaroo_labs-dag-DagNode)\[V\] ref\] ref

---

### edges

```pony
fun box edges()
: Iterator[(this->DagNode[V] ref , this->DagNode[V] ref)] ref
```

#### Returns

* [Iterator](builtin-Iterator)\[(this->[DagNode](wallaroo_labs-dag-DagNode)\[V\] ref , this->[DagNode](wallaroo_labs-dag-DagNode)\[V\] ref)\] ref

---

### add_edge

```pony
fun ref add_edge(
  from_id: U128 val,
  to_id: U128 val)
: None val ?
```
#### Parameters

*   from_id: [U128](builtin-U128) val
*   to_id: [U128](builtin-U128) val

#### Returns

* [None](builtin-None) val ?

---

### is_empty

```pony
fun box is_empty()
: Bool val
```

#### Returns

* [Bool](builtin-Bool) val

---

### clone

```pony
fun box clone()
: Dag[V] val ?
```

#### Returns

* [Dag](wallaroo_labs-dag-Dag)\[V\] val ?

---

### string

```pony
fun box string()
: String val
```

#### Returns

* [String](builtin-String) val

---

## Private Functions

### _gen_guid

```pony
fun box _gen_guid()
: U128 val
```

#### Returns

* [U128](builtin-U128) val

---

