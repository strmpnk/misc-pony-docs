# TCPSourceConfigCLIParser

```pony
primitive val TCPSourceConfigCLIParser
```

## Constructors

### create

```pony
new val create()
: TCPSourceConfigCLIParser val^
```

#### Returns

* [TCPSourceConfigCLIParser](wallaroo-core-source-tcp_source-TCPSourceConfigCLIParser) val^

---

## Public Functions

### apply

```pony
fun box apply(
  args: Array[String val] val)
: Array[TCPSourceConfigOptions val] val ?
```
#### Parameters

*   args: [Array](builtin-Array)\[[String](builtin-String) val\] val

#### Returns

* [Array](builtin-Array)\[[TCPSourceConfigOptions](wallaroo-core-source-tcp_source-TCPSourceConfigOptions) val\] val ?

---

### eq

```pony
fun box eq(
  that: TCPSourceConfigCLIParser val)
: Bool val
```
#### Parameters

*   that: [TCPSourceConfigCLIParser](wallaroo-core-source-tcp_source-TCPSourceConfigCLIParser) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: TCPSourceConfigCLIParser val)
: Bool val
```
#### Parameters

*   that: [TCPSourceConfigCLIParser](wallaroo-core-source-tcp_source-TCPSourceConfigCLIParser) val

#### Returns

* [Bool](builtin-Bool) val

---

## Private Functions

### _from_input_string

```pony
fun box _from_input_string(
  inputs: String val)
: Array[TCPSourceConfigOptions val] val ?
```
#### Parameters

*   inputs: [String](builtin-String) val

#### Returns

* [Array](builtin-Array)\[[TCPSourceConfigOptions](wallaroo-core-source-tcp_source-TCPSourceConfigOptions) val\] val ?

---

