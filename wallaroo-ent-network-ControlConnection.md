# ControlConnection

```pony
actor tag ControlConnection
```

## Constructors

### create

```pony
new tag create()
: ControlConnection tag^
```

#### Returns

* [ControlConnection](wallaroo-ent-network-ControlConnection) tag^

---

## Public Behaviours

### connected

```pony
be connected(
  conn: TCPConnection tag)
```
#### Parameters

*   conn: [TCPConnection](net-TCPConnection) tag

---

### closed

```pony
be closed(
  conn: TCPConnection tag)
```
#### Parameters

*   conn: [TCPConnection](net-TCPConnection) tag

---

### write

```pony
be write(
  data: (String val | Array[U8 val] val))
```
#### Parameters

*   data: ([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)

---

### writev

```pony
be writev(
  data: ByteSeqIter val)
```
#### Parameters

*   data: [ByteSeqIter](builtin-ByteSeqIter) val

---

### dispose

```pony
be dispose()
```

---

