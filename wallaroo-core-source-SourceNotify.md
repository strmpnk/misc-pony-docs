# SourceNotify

```pony
interface ref SourceNotify
```

## Public Functions

### routes

```pony
fun ref routes()
: Array[Consumer tag] val
```

#### Returns

* [Array](builtin-Array)\[[Consumer](wallaroo-core-common-Consumer) tag\] val

---

### update_router

```pony
fun ref update_router(
  router: Router val)
: None val
```
#### Parameters

*   router: [Router](wallaroo-core-topology-Router) val

#### Returns

* [None](builtin-None) val

---

### update_boundaries

```pony
fun ref update_boundaries(
  obs: HashMap[String val, OutgoingBoundary tag, HashEq[String val] val] box)
: None val
```
#### Parameters

*   obs: [HashMap](collections-HashMap)\[[String](builtin-String) val, [OutgoingBoundary](wallaroo-core-boundary-OutgoingBoundary) tag, [HashEq](collections-HashEq)\[[String](builtin-String) val\] val\] box

#### Returns

* [None](builtin-None) val

---

