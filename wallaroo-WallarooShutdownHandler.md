# WallarooShutdownHandler

Shutdown gracefully on SIGTERM and SIGINT


```pony
class ref WallarooShutdownHandler is
  SignalNotify ref
```

#### Implements

* [SignalNotify](signals-SignalNotify) ref

---

## Constructors

### create

```pony
new iso create(
  c: Connections tag,
  r: RecoveryFileCleaner tag,
  a: AmbientAuth val)
: WallarooShutdownHandler iso^
```
#### Parameters

*   c: [Connections](wallaroo-ent-network-Connections) tag
*   r: [RecoveryFileCleaner](wallaroo-core-common-RecoveryFileCleaner) tag
*   a: [AmbientAuth](builtin-AmbientAuth) val

#### Returns

* [WallarooShutdownHandler](wallaroo-WallarooShutdownHandler) iso^

---

## Public Functions

### apply

```pony
fun ref apply(
  count: U32 val)
: Bool val
```
#### Parameters

*   count: [U32](builtin-U32) val

#### Returns

* [Bool](builtin-Bool) val

---

### dispose

```pony
fun ref dispose()
: None val
```

#### Returns

* [None](builtin-None) val

---

