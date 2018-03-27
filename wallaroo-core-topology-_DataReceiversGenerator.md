# _DataReceiversGenerator

```pony
primitive val _DataReceiversGenerator
```

## Constructors

### create

```pony
new val create()
: _DataReceiversGenerator val^
```

#### Returns

* [_DataReceiversGenerator](wallaroo-core-topology-_DataReceiversGenerator) val^

---

## Public Functions

### apply

```pony
fun box apply(
  env: Env val,
  auth: AmbientAuth val)
: DataReceivers tag
```
#### Parameters

*   env: [Env](builtin-Env) val
*   auth: [AmbientAuth](builtin-AmbientAuth) val

#### Returns

* [DataReceivers](wallaroo-ent-data_receiver-DataReceivers) tag

---

### eq

```pony
fun box eq(
  that: _DataReceiversGenerator val)
: Bool val
```
#### Parameters

*   that: [_DataReceiversGenerator](wallaroo-core-topology-_DataReceiversGenerator) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: _DataReceiversGenerator val)
: Bool val
```
#### Parameters

*   that: [_DataReceiversGenerator](wallaroo-core-topology-_DataReceiversGenerator) val

#### Returns

* [Bool](builtin-Bool) val

---

