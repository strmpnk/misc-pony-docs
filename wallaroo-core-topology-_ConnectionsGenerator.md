# _ConnectionsGenerator

```pony
primitive val _ConnectionsGenerator
```

## Constructors

### create

```pony
new val create()
: _ConnectionsGenerator val^
```

#### Returns

* [_ConnectionsGenerator](wallaroo-core-topology-_ConnectionsGenerator) val^

---

## Public Functions

### apply

```pony
fun box apply(
  env: Env val,
  auth: AmbientAuth val)
: Connections tag
```
#### Parameters

*   env: [Env](builtin-Env) val
*   auth: [AmbientAuth](builtin-AmbientAuth) val

#### Returns

* [Connections](wallaroo-ent-network-Connections) tag

---

### eq

```pony
fun box eq(
  that: _ConnectionsGenerator val)
: Bool val
```
#### Parameters

*   that: [_ConnectionsGenerator](wallaroo-core-topology-_ConnectionsGenerator) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: _ConnectionsGenerator val)
: Bool val
```
#### Parameters

*   that: [_ConnectionsGenerator](wallaroo-core-topology-_ConnectionsGenerator) val

#### Returns

* [Bool](builtin-Bool) val

---

