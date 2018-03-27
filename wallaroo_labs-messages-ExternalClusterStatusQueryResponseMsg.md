# ExternalClusterStatusQueryResponseMsg

```pony
class val ExternalClusterStatusQueryResponseMsg is
  ExternalMsg val
```

#### Implements

* [ExternalMsg](wallaroo_labs-messages-ExternalMsg) val

---

## Constructors

### create

```pony
new val create(
  worker_count': U64 val,
  worker_names': Array[String val] val,
  processing_messages': Bool val,
  json': String val)
: ExternalClusterStatusQueryResponseMsg val^
```
#### Parameters

*   worker_count': [U64](builtin-U64) val
*   worker_names': [Array](builtin-Array)\[[String](builtin-String) val\] val
*   processing_messages': [Bool](builtin-Bool) val
*   json': [String](builtin-String) val

#### Returns

* [ExternalClusterStatusQueryResponseMsg](wallaroo_labs-messages-ExternalClusterStatusQueryResponseMsg) val^

---

## Public fields

* let worker_count: [U64](builtin-U64) val

---

* let worker_names: [Array](builtin-Array)\[[String](builtin-String) val\] val

---

* let processing_messages: [Bool](builtin-Bool) val

---

* let json: [String](builtin-String) val

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

