# KeyComparator

```pony
primitive val KeyComparator
```

## Constructors

### create

```pony
new val create()
: KeyComparator val^
```

#### Returns

* [KeyComparator](pony-kafka-KeyComparator) val^

---

## Public Functions

### eq

```pony
fun box eq(
  a: (String val | Array[U8 val] val | None val),
  b: (String val | Array[U8 val] val | None val))
: Bool val ?
```
#### Parameters

*   a: ([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val | [None](builtin-None) val)
*   b: ([String](builtin-String) val | [Array](builtin-Array)\[[U8](builtin-U8) val\] val | [None](builtin-None) val)

#### Returns

* [Bool](builtin-Bool) val ?

---

### ne

```pony
fun box ne(
  that: KeyComparator val)
: Bool val
```
#### Parameters

*   that: [KeyComparator](pony-kafka-KeyComparator) val

#### Returns

* [Bool](builtin-Bool) val

---

