# KeyedStateAddresses\[Key: ([Hashable](collections-Hashable) val & [Equatable](builtin-Equatable)\[Key\] val)\]

```pony
class ref KeyedStateAddresses[Key: (Hashable val & Equatable[Key] val)]
```

## Constructors

### create

```pony
new val create(
  a: HashMap[Key, (Step tag | ProxyRouter val), HashEq[Key] val] val)
: KeyedStateAddresses[Key] val^
```
#### Parameters

*   a: [HashMap](collections-HashMap)\[Key, ([Step](wallaroo-core-topology-Step) tag | [ProxyRouter](wallaroo-core-topology-ProxyRouter) val), [HashEq](collections-HashEq)\[Key\] val\] val

#### Returns

* [KeyedStateAddresses](wallaroo-core-topology-KeyedStateAddresses)\[Key\] val^

---

## Public Functions

### apply

```pony
fun box apply(
  k: Any val)
: (Step tag | ProxyRouter val | None val)
```
#### Parameters

*   k: [Any](builtin-Any) val

#### Returns

* ([Step](wallaroo-core-topology-Step) tag | [ProxyRouter](wallaroo-core-topology-ProxyRouter) val | [None](builtin-None) val)

---

### register_routes

```pony
fun box register_routes(
  router: Router val,
  route_builder: RouteBuilder val)
: None val
```
#### Parameters

*   router: [Router](wallaroo-core-topology-Router) val
*   route_builder: [RouteBuilder](wallaroo-core-routing-RouteBuilder) val

#### Returns

* [None](builtin-None) val

---

### steps

```pony
fun box steps()
: Array[Consumer tag] val
```

#### Returns

* [Array](builtin-Array)\[[Consumer](wallaroo-core-common-Consumer) tag\] val

---

