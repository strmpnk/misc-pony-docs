# OutgoingBoundaryBuilder

```pony
class val OutgoingBoundaryBuilder
```

## Constructors

### create

```pony
new val create(
  auth: AmbientAuth val,
  name: String val,
  r: MetricsReporter iso,
  h: String val,
  s: String val,
  spike_config: (SpikeConfig val | None val) = seq)
: OutgoingBoundaryBuilder val^
```
#### Parameters

*   auth: [AmbientAuth](builtin-AmbientAuth) val
*   name: [String](builtin-String) val
*   r: [MetricsReporter](wallaroo-core-metrics-MetricsReporter) iso
*   h: [String](builtin-String) val
*   s: [String](builtin-String) val
*   spike_config: ([SpikeConfig](wallaroo-ent-spike-SpikeConfig) val | [None](builtin-None) val) = seq

#### Returns

* [OutgoingBoundaryBuilder](wallaroo-core-boundary-OutgoingBoundaryBuilder) val^

---

## Public Functions

### apply

```pony
fun box apply(
  step_id: U128 val)
: OutgoingBoundary tag
```
#### Parameters

*   step_id: [U128](builtin-U128) val

#### Returns

* [OutgoingBoundary](wallaroo-core-boundary-OutgoingBoundary) tag

---

### build_and_initialize

Called when creating a boundary post cluster initialization


```pony
fun box build_and_initialize(
  step_id: U128 val,
  layout_initializer: LayoutInitializer tag)
: OutgoingBoundary tag
```
#### Parameters

*   step_id: [U128](builtin-U128) val
*   layout_initializer: [LayoutInitializer](wallaroo-core-initialization-LayoutInitializer) tag

#### Returns

* [OutgoingBoundary](wallaroo-core-boundary-OutgoingBoundary) tag

---

