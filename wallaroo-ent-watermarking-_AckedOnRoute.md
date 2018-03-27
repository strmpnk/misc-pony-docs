# _AckedOnRoute

Class used to keep track of acking on a per route basis.
No route_id is in this class as this class is used as the value in a map.


```pony
class ref _AckedOnRoute
```

## Constructors

### create

```pony
new iso create()
: _AckedOnRoute iso^
```

#### Returns

* [_AckedOnRoute](wallaroo-ent-watermarking-_AckedOnRoute) iso^

---

## Public Functions

### sent

```pony
fun ref sent(
  o_seq_id: U64 val)
: None val
```
#### Parameters

*   o_seq_id: [U64](builtin-U64) val

#### Returns

* [None](builtin-None) val

---

### ack_received

```pony
fun ref ack_received(
  seq_id: U64 val)
: None val
```
#### Parameters

*   seq_id: [U64](builtin-U64) val

#### Returns

* [None](builtin-None) val

---

### is_fully_acked

```pony
fun box is_fully_acked()
: Bool val
```

#### Returns

* [Bool](builtin-Bool) val

---

### highest_seq_id_acked

```pony
fun box highest_seq_id_acked()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### highest_seq_id_sent

```pony
fun box highest_seq_id_sent()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

