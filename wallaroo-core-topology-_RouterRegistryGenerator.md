# _RouterRegistryGenerator

```pony
primitive val _RouterRegistryGenerator
```

## Constructors

### create

```pony
new val create()
: _RouterRegistryGenerator val^
```

#### Returns

* [_RouterRegistryGenerator](wallaroo-core-topology-_RouterRegistryGenerator) val^

---

## Public Functions

### apply

```pony
fun box apply(
  env: Env val,
  auth: AmbientAuth val)
: RouterRegistry tag
```
#### Parameters

*   env: [Env](builtin-Env) val
*   auth: [AmbientAuth](builtin-AmbientAuth) val

#### Returns

* [RouterRegistry](wallaroo-ent-router_registry-RouterRegistry) tag

---

### eq

```pony
fun box eq(
  that: _RouterRegistryGenerator val)
: Bool val
```
#### Parameters

*   that: [_RouterRegistryGenerator](wallaroo-core-topology-_RouterRegistryGenerator) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: _RouterRegistryGenerator val)
: Bool val
```
#### Parameters

*   that: [_RouterRegistryGenerator](wallaroo-core-topology-_RouterRegistryGenerator) val

#### Returns

* [Bool](builtin-Bool) val

---

