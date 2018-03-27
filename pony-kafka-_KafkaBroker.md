# _KafkaBroker

```pony
class ref _KafkaBroker is
  Equatable[_KafkaBroker box] ref
```

#### Implements

* [Equatable](builtin-Equatable)\[[_KafkaBroker](pony-kafka-_KafkaBroker) box\] ref

---

## Constructors

### create

```pony
new ref create(
  node_id': I32 val,
  host': String val,
  port': I32 val,
  rack': String val = seq)
: _KafkaBroker ref^
```
#### Parameters

*   node_id': [I32](builtin-I32) val
*   host': [String](builtin-String) val
*   port': [I32](builtin-I32) val
*   rack': [String](builtin-String) val = seq

#### Returns

* [_KafkaBroker](pony-kafka-_KafkaBroker) ref^

---

## Public fields

* var node_id: [I32](builtin-I32) val

---

* let host: [String](builtin-String) val

---

* let port: [I32](builtin-I32) val

---

* var rack: [String](builtin-String) val

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

### set_node_id

```pony
fun ref set_node_id(
  node_id': I32 val)
: None val
```
#### Parameters

*   node_id': [I32](builtin-I32) val

#### Returns

* [None](builtin-None) val

---

### set_rack

```pony
fun ref set_rack(
  rack': String val)
: None val
```
#### Parameters

*   rack': [String](builtin-String) val

#### Returns

* [None](builtin-None) val

---

### hash

```pony
fun box hash()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### eq

```pony
fun box eq(
  that: _KafkaBroker box)
: Bool val
```
#### Parameters

*   that: [_KafkaBroker](pony-kafka-_KafkaBroker) box

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: _KafkaBroker box)
: Bool val
```
#### Parameters

*   that: [_KafkaBroker](pony-kafka-_KafkaBroker) box

#### Returns

* [Bool](builtin-Bool) val

---

