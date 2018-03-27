# _PreTCPConnectionControlSender

```pony
class ref _PreTCPConnectionControlSender is
  _TCPConnectionControlSender ref
```

#### Implements

* [_TCPConnectionControlSender](wallaroo-ent-network-_TCPConnectionControlSender) ref

---

## Constructors

### create

```pony
new iso create()
: _PreTCPConnectionControlSender iso^
```

#### Returns

* [_PreTCPConnectionControlSender](wallaroo-ent-network-_PreTCPConnectionControlSender) iso^

---

## Public Functions

### write

```pony
fun ref write(
  data: (String val | Array[U8 val] val))
: None val
```
#### Parameters

*   data: ([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)

#### Returns

* [None](builtin-None) val

---

### writev

```pony
fun ref writev(
  data: ByteSeqIter val)
: None val
```
#### Parameters

*   data: [ByteSeqIter](builtin-ByteSeqIter) val

#### Returns

* [None](builtin-None) val

---

### flush

```pony
fun ref flush(
  conn: TCPConnection tag)
: None val
```
#### Parameters

*   conn: [TCPConnection](net-TCPConnection) tag

#### Returns

* [None](builtin-None) val

---

### dispose

```pony
fun box dispose()
: None val
```

#### Returns

* [None](builtin-None) val

---

