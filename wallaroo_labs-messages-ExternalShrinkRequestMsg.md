# ExternalShrinkRequestMsg

```pony
class val ExternalShrinkRequestMsg is
  ExternalMsg val
```

#### Implements

* [ExternalMsg](wallaroo_labs-messages-ExternalMsg) val

---

## Constructors

### create

```pony
new val create(
  query': Bool val,
  node_names': Array[String val] val,
  num_nodes': U64 val)
: ExternalShrinkRequestMsg val^
```
#### Parameters

*   query': [Bool](builtin-Bool) val
*   node_names': [Array](builtin-Array)\[[String](builtin-String) val\] val
*   num_nodes': [U64](builtin-U64) val

#### Returns

* [ExternalShrinkRequestMsg](wallaroo_labs-messages-ExternalShrinkRequestMsg) val^

---

## Public fields

* let query: [Bool](builtin-Bool) val

---

* let node_names: [Array](builtin-Array)\[[String](builtin-String) val\] val

---

* let num_nodes: [U64](builtin-U64) val

---

## Public Functions

### string

```pony
fun box string()
: String val
```

#### Returns

* [String](builtin-String) val

---

### the_string

```pony
fun box the_string()
: None val
```

#### Returns

* [None](builtin-None) val

---

