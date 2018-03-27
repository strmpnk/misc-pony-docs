# WallarooConfig

```pony
primitive val WallarooConfig
```

## Constructors

### create

```pony
new val create()
: WallarooConfig val^
```

#### Returns

* [WallarooConfig](wallaroo-WallarooConfig) val^

---

## Public Functions

### application_args

```pony
fun box application_args(
  args: Array[String val] val)
: Array[String val] val ?
```
#### Parameters

*   args: [Array](builtin-Array)\[[String](builtin-String) val\] val

#### Returns

* [Array](builtin-Array)\[[String](builtin-String) val\] val ?

---

### wallaroo_args

```pony
fun box wallaroo_args(
  args: Array[String val] val)
: StartupOptions ref ?
```
#### Parameters

*   args: [Array](builtin-Array)\[[String](builtin-String) val\] val

#### Returns

* [StartupOptions](wallaroo-StartupOptions) ref ?

---

### wactor_args

```pony
fun box wactor_args(
  args: Array[String val] val)
: StartupOptions ref ?
```
#### Parameters

*   args: [Array](builtin-Array)\[[String](builtin-String) val\] val

#### Returns

* [StartupOptions](wallaroo-StartupOptions) ref ?

---

### eq

```pony
fun box eq(
  that: WallarooConfig val)
: Bool val
```
#### Parameters

*   that: [WallarooConfig](wallaroo-WallarooConfig) val

#### Returns

* [Bool](builtin-Bool) val

---

### ne

```pony
fun box ne(
  that: WallarooConfig val)
: Bool val
```
#### Parameters

*   that: [WallarooConfig](wallaroo-WallarooConfig) val

#### Returns

* [Bool](builtin-Bool) val

---

## Private Functions

### _parse

```pony
fun box _parse(
  args: Array[String val] val,
  handle_help: Bool val,
  include_input_addrs: Bool val = seq)
: (StartupOptions ref , Array[String val] val) ?
```
#### Parameters

*   args: [Array](builtin-Array)\[[String](builtin-String) val\] val
*   handle_help: [Bool](builtin-Bool) val
*   include_input_addrs: [Bool](builtin-Bool) val = seq

#### Returns

* ([StartupOptions](wallaroo-StartupOptions) ref , [Array](builtin-Array)\[[String](builtin-String) val\] val) ?

---

