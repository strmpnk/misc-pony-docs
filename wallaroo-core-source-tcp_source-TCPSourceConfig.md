# TCPSourceConfig\[In: [Any](builtin-Any) val\]

```pony
class val TCPSourceConfig[In: Any val]
```

## Constructors

### create

```pony
new val create(
  handler': FramedSourceHandler[In] val,
  host': String val,
  service': String val)
: TCPSourceConfig[In] val^
```
#### Parameters

*   handler': [FramedSourceHandler](wallaroo-core-source-FramedSourceHandler)\[In\] val
*   host': [String](builtin-String) val
*   service': [String](builtin-String) val

#### Returns

* [TCPSourceConfig](wallaroo-core-source-tcp_source-TCPSourceConfig)\[In\] val^

---

### from_options

```pony
new val from_options(
  handler': FramedSourceHandler[In] val,
  opts: TCPSourceConfigOptions val)
: TCPSourceConfig[In] val^
```
#### Parameters

*   handler': [FramedSourceHandler](wallaroo-core-source-FramedSourceHandler)\[In\] val
*   opts: [TCPSourceConfigOptions](wallaroo-core-source-tcp_source-TCPSourceConfigOptions) val

#### Returns

* [TCPSourceConfig](wallaroo-core-source-tcp_source-TCPSourceConfig)\[In\] val^

---

## Public Functions

### source_listener_builder_builder

```pony
fun box source_listener_builder_builder()
: TCPSourceListenerBuilderBuilder val
```

#### Returns

* [TCPSourceListenerBuilderBuilder](wallaroo-core-source-tcp_source-TCPSourceListenerBuilderBuilder) val

---

### source_builder

```pony
fun box source_builder(
  app_name: String val,
  name: String val)
: TypedTCPSourceBuilderBuilder[In] val
```
#### Parameters

*   app_name: [String](builtin-String) val
*   name: [String](builtin-String) val

#### Returns

* [TypedTCPSourceBuilderBuilder](wallaroo-core-source-tcp_source-TypedTCPSourceBuilderBuilder)\[In\] val

---

