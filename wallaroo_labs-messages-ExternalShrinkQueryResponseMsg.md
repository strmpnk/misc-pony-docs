# ExternalShrinkQueryResponseMsg

```pony
class val ExternalShrinkQueryResponseMsg is
  ExternalMsg val
```

#### Implements

* [ExternalMsg](wallaroo_labs-messages-ExternalMsg) val

---

## Constructors

### create

```pony
new val create(
  node_names': Array[String val] val,
  num_nodes': U64 val)
: ExternalShrinkQueryResponseMsg val^
```
#### Parameters

*   node_names': [Array](builtin-Array)\[[String](builtin-String) val\] val
*   num_nodes': [U64](builtin-U64) val

#### Returns

* [ExternalShrinkQueryResponseMsg](wallaroo_labs-messages-ExternalShrinkQueryResponseMsg) val^

---

## Public fields

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

