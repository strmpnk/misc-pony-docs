# _BoundaryGenerator

```pony
primitive val _BoundaryGenerator
```

## Constructors

### create

```pony
new val create()
: _BoundaryGenerator val^
```

#### Returns

* [_BoundaryGenerator](wallaroo-core-topology-_BoundaryGenerator) val^

---

## Public Functions

### apply

```pony
fun box apply(
  worker_name: String val,
  auth: AmbientAuth val)
: OutgoingBoundary tag
```
#### Parameters

*   worker_name: [String](builtin-String) val
*   auth: [AmbientAuth](builtin-AmbientAuth) val

#### Returns

* [OutgoingBoundary](wallaroo-core-boundary-OutgoingBoundary) tag

---

### eq

```pony
fun box eq(
  that: _BoundaryGenerator val)
: Bool val
```
#### Parameters

*   that: [_BoundaryGenerator](wallaroo-core-topology-_BoundaryGenerator) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: _BoundaryGenerator val)
: Bool val
```
#### Parameters

*   that: [_BoundaryGenerator](wallaroo-core-topology-_BoundaryGenerator) val

#### Returns

* [Bool](builtin-Bool) val

---

