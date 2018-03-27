# TCPSinkConfigCLIParser

```pony
primitive val TCPSinkConfigCLIParser
```

## Constructors

### create

```pony
new val create()
: TCPSinkConfigCLIParser val^
```

#### Returns

* [TCPSinkConfigCLIParser](wallaroo-core-sink-tcp_sink-TCPSinkConfigCLIParser) val^

---

## Public Functions

### apply

```pony
fun box apply(
  args: Array[String val] val)
: Array[TCPSinkConfigOptions val] val ?
```
#### Parameters

*   args: [Array](builtin-Array)\[[String](builtin-String) val\] val

#### Returns

* [Array](builtin-Array)\[[TCPSinkConfigOptions](wallaroo-core-sink-tcp_sink-TCPSinkConfigOptions) val\] val ?

---

### eq

```pony
fun box eq(
  that: TCPSinkConfigCLIParser val)
: Bool val
```
#### Parameters

*   that: [TCPSinkConfigCLIParser](wallaroo-core-sink-tcp_sink-TCPSinkConfigCLIParser) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: TCPSinkConfigCLIParser val)
: Bool val
```
#### Parameters

*   that: [TCPSinkConfigCLIParser](wallaroo-core-sink-tcp_sink-TCPSinkConfigCLIParser) val

#### Returns

* [Bool](builtin-Bool) val

---

## Private Functions

### _from_output_string

```pony
fun box _from_output_string(
  outputs: String val)
: Array[TCPSinkConfigOptions val] val ?
```
#### Parameters

*   outputs: [String](builtin-String) val

#### Returns

* [Array](builtin-Array)\[[TCPSinkConfigOptions](wallaroo-core-sink-tcp_sink-TCPSinkConfigOptions) val\] val ?

---

