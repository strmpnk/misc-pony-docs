# ByteSeqComparator

```pony
primitive val ByteSeqComparator
```

## Constructors

### create

```pony
new val create()
: ByteSeqComparator val^
```

#### Returns

* [ByteSeqComparator](pony-kafka-ByteSeqComparator) val^

---

## Public Functions

### eq

```pony
fun box eq(
  a: (String val | Array[U8 val] val),
  b: (String val | Array[U8 val] val))
: Bool val ?
```
#### Parameters

*   a: ([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)
*   b: ([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val)

#### Returns

* [Bool](builtin-Bool) val ?

---

### ne

```pony
fun box ne(
  that: ByteSeqComparator val)
: Bool val
```
#### Parameters

*   that: [ByteSeqComparator](pony-kafka-ByteSeqComparator) val

#### Returns

* [Bool](builtin-Bool) val

---

