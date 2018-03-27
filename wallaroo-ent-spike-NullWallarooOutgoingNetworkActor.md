# NullWallarooOutgoingNetworkActor

```pony
class ref NullWallarooOutgoingNetworkActor is
  WallarooOutgoingNetworkActor ref
```

#### Implements

* [WallarooOutgoingNetworkActor](wallaroo-ent-network-WallarooOutgoingNetworkActor) ref

---

## Constructors

### create

```pony
new ref create(
  h: TestHelper val,
  should_close: Bool val)
: NullWallarooOutgoingNetworkActor ref^
```
#### Parameters

*   h: [TestHelper](ponytest-TestHelper) val
*   should_close: [Bool](builtin-Bool) val

#### Returns

* [NullWallarooOutgoingNetworkActor](wallaroo-ent-spike-NullWallarooOutgoingNetworkActor) ref^

---

## Public Functions

### set_nodelay

```pony
fun ref set_nodelay(
  state: Bool val)
: None val
```
#### Parameters

*   state: [Bool](builtin-Bool) val

#### Returns

* [None](builtin-None) val

---

### expect

```pony
fun ref expect(
  qty: USize val = seq)
: None val
```
#### Parameters

*   qty: [USize](builtin-USize) val = seq

#### Returns

* [None](builtin-None) val

---

### receive_ack

```pony
fun ref receive_ack(
  seq_id: U64 val)
: None val
```
#### Parameters

*   seq_id: [U64](builtin-U64) val

#### Returns

* [None](builtin-None) val

---

### receive_connect_ack

```pony
fun ref receive_connect_ack(
  seq_id: U64 val)
: None val
```
#### Parameters

*   seq_id: [U64](builtin-U64) val

#### Returns

* [None](builtin-None) val

---

### start_normal_sending

```pony
fun ref start_normal_sending()
: None val
```

#### Returns

* [None](builtin-None) val

---

### close

```pony
fun ref close()
: None val
```

#### Returns

* [None](builtin-None) val

---

