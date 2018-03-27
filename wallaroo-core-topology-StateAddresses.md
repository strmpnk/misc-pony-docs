# StateAddresses

```pony
interface ref StateAddresses
```

## Public Functions

### apply

```pony
fun box apply(
  key: Any val)
: (Step tag | ProxyRouter val | None val)
```
#### Parameters

*   key: [Any](builtin-Any) val

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

