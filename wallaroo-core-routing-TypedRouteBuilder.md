# TypedRouteBuilder\[In: [Any](builtin-Any) val\]

```pony
primitive val TypedRouteBuilder[In: Any val] is
  RouteBuilder val
```

#### Implements

* [RouteBuilder](wallaroo-core-routing-RouteBuilder) val

---

## Constructors

### create

```pony
new val create()
: TypedRouteBuilder[In] val^
```

#### Returns

* [TypedRouteBuilder](wallaroo-core-routing-TypedRouteBuilder)\[In\] val^

---

## Public Functions

### apply

```pony
fun box apply(
  step: Producer ref,
  consumer: Consumer tag,
  metrics_reporter: MetricsReporter ref)
: Route ref
```
#### Parameters

*   step: [Producer](wallaroo-core-common-Producer) ref
*   consumer: [Consumer](wallaroo-core-common-Consumer) tag
*   metrics_reporter: [MetricsReporter](wallaroo-core-metrics-MetricsReporter) ref

#### Returns

* [Route](wallaroo-core-routing-Route) ref

---

### eq

```pony
fun box eq(
  that: TypedRouteBuilder[In] val)
: Bool val
```
#### Parameters

*   that: [TypedRouteBuilder](wallaroo-core-routing-TypedRouteBuilder)\[In\] val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: TypedRouteBuilder[In] val)
: Bool val
```
#### Parameters

*   that: [TypedRouteBuilder](wallaroo-core-routing-TypedRouteBuilder)\[In\] val

#### Returns

* [Bool](builtin-Bool) val

---

