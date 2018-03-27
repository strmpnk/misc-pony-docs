# Watermarker

Tracks watermarks across all routes so we can propose a new watermark.


```pony
class ref Watermarker
```

## Constructors

### create

```pony
new iso create()
: Watermarker iso^
```

#### Returns

* [Watermarker](wallaroo-ent-watermarking-Watermarker) iso^

---

## Public Functions

### add_route

```pony
fun ref add_route(
  id: U64 val)
: None val
```
#### Parameters

*   id: [U64](builtin-U64) val

#### Returns

* [None](builtin-None) val

---

### remove_route

```pony
fun ref remove_route(
  id: U64 val)
: None val
```
#### Parameters

*   id: [U64](builtin-U64) val

#### Returns

* [None](builtin-None) val

---

### sent

```pony
fun ref sent(
  o_route_id: U64 val,
  o_seq_id: U64 val)
: None val
```
#### Parameters

*   o_route_id: [U64](builtin-U64) val
*   o_seq_id: [U64](builtin-U64) val

#### Returns

* [None](builtin-None) val

---

### filtered

Filter out a message or otherwise have this be the end of the line


```pony
fun ref filtered(
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
  route_id: U64 val,
  seq_id: U64 val)
: None val
```
#### Parameters

*   route_id: [U64](builtin-U64) val
*   seq_id: [U64](builtin-U64) val

#### Returns

* [None](builtin-None) val

---

### propose_watermark

```pony
fun ref propose_watermark()
: U64 val
```

#### Returns

* [U64](builtin-U64) val

---

### unacked_route_ids

```pony
fun box unacked_route_ids()
: Array[U64 val] ref
```

#### Returns

* [Array](builtin-Array)\[[U64](builtin-U64) val\] ref

---

