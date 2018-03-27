# BoundaryOnlyRouteBuilder

```pony
primitive val BoundaryOnlyRouteBuilder is
  RouteBuilder val
```

#### Implements

* [RouteBuilder](wallaroo-core-routing-RouteBuilder) val

---

## Constructors

### create

```pony
new val create()
: BoundaryOnlyRouteBuilder val^
```

#### Returns

* [BoundaryOnlyRouteBuilder](wallaroo-core-routing-BoundaryOnlyRouteBuilder) val^

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
  that: BoundaryOnlyRouteBuilder val)
: Bool val
```
#### Parameters

*   that: [BoundaryOnlyRouteBuilder](wallaroo-core-routing-BoundaryOnlyRouteBuilder) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: BoundaryOnlyRouteBuilder val)
: Bool val
```
#### Parameters

*   that: [BoundaryOnlyRouteBuilder](wallaroo-core-routing-BoundaryOnlyRouteBuilder) val

#### Returns

* [Bool](builtin-Bool) val

---

