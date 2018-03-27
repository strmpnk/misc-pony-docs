# StateChangeRepository\[S: [State](wallaroo-core-state-State) ref\]

```pony
class ref StateChangeRepository[S: State ref]
```

## Constructors

### create

```pony
new ref create()
: StateChangeRepository[S] ref^
```

#### Returns

* [StateChangeRepository](wallaroo-core-state-StateChangeRepository)\[S\] ref^

---

## Public Functions

### make_and_register

```pony
fun ref make_and_register(
  scb: StateChangeBuilder[S] val)
: U64 val
```
#### Parameters

*   scb: [StateChangeBuilder](wallaroo-core-state-StateChangeBuilder)\[S\] val

#### Returns

* [U64](builtin-U64) val

---

### apply

```pony
fun ref apply(
  index: U64 val)
: StateChange[S] ref ?
```
#### Parameters

*   index: [U64](builtin-U64) val

#### Returns

* [StateChange](wallaroo-core-state-StateChange)\[S\] ref ?

---

### lookup_by_name

```pony
fun ref lookup_by_name(
  name: String val)
: StateChange[S] ref ?
```
#### Parameters

*   name: [String](builtin-String) val

#### Returns

* [StateChange](wallaroo-core-state-StateChange)\[S\] ref ?

---

### size

```pony
fun box size()
: USize val
```

#### Returns

* [USize](builtin-USize) val

---

### contains

```pony
fun box contains(
  name: String val)
: Bool val
```
#### Parameters

*   name: [String](builtin-String) val

#### Returns

* [Bool](builtin-Bool) val

---

